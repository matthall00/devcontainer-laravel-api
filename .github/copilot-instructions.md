# GitHub Copilot General Instructions

## Project Overview

This is a Laravel REST API starter project that follows modern development practices, RESTful architecture, and Laravel conventions.

## Code Style & Standards

- Follow PSR-12 coding standards
- Use type hints and return types for methods
- Implement SOLID principles
- Use dependency injection where appropriate
- Keep methods small and focused (single responsibility)
- Use meaningful variable and function names
- Add PHPDoc blocks for classes and methods

## Architecture Patterns

- Follow Repository pattern for data access
- Use Service classes for business logic
- Implement Request classes for validation
- Use Resources for API responses
- Follow Controller-Service-Repository pattern

## API Guidelines

- Use plural resource names for endpoints
- Follow REST conventions for HTTP methods
- Implement proper HTTP status codes
- Version APIs appropriately
- Use camelCase for JSON response fields
- Include proper error handling and messages

## Testing

- Write PHPUnit tests for new features
- Include feature and unit tests
- Test happy paths and edge cases
- Mock external services
- Use factories for test data

## Security

- Validate all input data
- Sanitize outputs
- Use proper authentication middleware
- Implement rate limiting
- Follow Laravel security best practices

## Database

- Use migrations for schema changes
- Include foreign key constraints
- Add appropriate indexes
- Use soft deletes where needed
- Follow naming conventions for tables and columns

## Performance

- Cache responses when appropriate
- Optimize database queries
- Use eager loading to prevent N+1 issues
- Implement pagination for list endpoints
- Monitor query performance

## Documentation

- Add API documentation using OpenAPI/Swagger
- Include setup instructions in README
- Document environment variables
- Add inline comments for complex logic

## Error Handling

- Use custom exception classes
- Implement consistent error responses
- Log errors appropriately
- Include meaningful error messages
- Handle validation errors consistently

## Example Patterns

```php
// Controller example
class UserController extends Controller
{
    public function store(StoreUserRequest $request): JsonResponse
    {
        $user = $this->userService->create($request->validated());
        return new UserResource($user);
    }
}

// Service example
class UserService
{
    public function create(array $data): User
    {
        return $this->userRepository->create($data);
    }
}

// Repository example
class UserRepository
{
    public function create(array $data): User
    {
        return User::create($data);
    }
}
```

## Common Pitfalls to Avoid

- Don't put business logic in controllers
- Avoid raw queries in models
- Don't skip validation
- Avoid heavy processing in controllers
- Don't expose sensitive information in responses
