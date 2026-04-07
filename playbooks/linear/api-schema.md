# API Schema Generator

Generate a structured API schema from natural-language endpoint descriptions. Demonstrates the `json` artifact type and `boolean` input type.

## SYSTEM

You are an API architect. Design clean, consistent APIs following industry standards. Produce schemas that are complete, well-documented, and ready for implementation.

## INPUTS

- `service_name` (string): Name of the API service
- `endpoints` (text): Natural-language description of the API endpoints
- `style` (enum: REST, GraphQL): API style to generate
- `include_examples` (boolean: true): Whether to include example values in the schema

## STEP 1: Extract Resources

Analyze the following endpoint descriptions for the {{service_name}} API:

{{endpoints}}

Extract and organize:
1. **Resources**: Each distinct entity or noun (e.g., User, Order, Product)
2. **Operations**: CRUD and custom actions for each resource
3. **Parameters**: Path params, query params, and request body fields with inferred types
4. **Relationships**: How resources reference each other (e.g., Order belongs to User)
5. **Authentication**: Any mentioned auth requirements

Respond with a JSON object:
{"resource_count": 3, "operation_count": 8}

@output(resource_summary, extract:"resource_count")

## STEP 2: Generate Schema

```if style == "REST"```

### STEP 2a: OpenAPI Schema

Generate an OpenAPI 3.0 JSON schema for the {{service_name}} API with {{resource_summary}} resources.

For each endpoint include:
- HTTP method and path
- Summary and description
- Request parameters and body schema with types
- Response schemas for success (2xx) and error (4xx, 5xx) cases
- Content-Type headers

```else```

### STEP 2b: GraphQL SDL

Generate a GraphQL schema (SDL format as a JSON string) for the {{service_name}} API with {{resource_summary}} resources.

Include:
- Type definitions for each resource
- Query type with list and single-item resolvers
- Mutation type for create, update, and delete operations
- Input types for mutation arguments
- Connection types for paginated lists

```endif```

@output(schema)

## STEP 3: Enrich Schema

Review the generated schema for {{service_name}} and add:

1. **Validation rules**: Field constraints (min/max length, patterns, required fields, enums)
2. **Descriptions**: Human-readable descriptions for every field and endpoint

If {{include_examples}} is true, add example values for each field that are realistic and consistent across related resources (e.g., an order's user_id should match an example user's id). If {{include_examples}} is false, skip adding example values.

3. **Error schemas**: Standardized error response format

Output the final, complete schema as valid JSON.

## ARTIFACTS

type: json
