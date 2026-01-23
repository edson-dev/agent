---
name: golang-backend
description: Go backend standards with clean architecture, boundaries, and tooling best practices.
allowed-tools: Read, Write, Edit, Glob, Grep
version: 1.0
priority: HIGH
---

# Golang Backend - Clean Architecture Enforcement

> Build Go backends with strict boundaries, clear contracts, and measurable quality.

---

## Core Principles

| Principle | Rule |
|----------|------|
| **Clean Architecture** | Entities → Use Cases → Interface Adapters → Infrastructure |
| **Dependency Rule** | Inner layers never import outer layers |
| **Ports & Adapters** | Interfaces in domain/use cases, implementations in infra |
| **Explicit Boundaries** | DTOs at edges, domain types inside |
| **Context First** | Every request carries context.Context |

---

## Project Layout

| Layer | Responsibility |
|------|----------------|
| `domain/` | Entities, value objects, domain services |
| `usecase/` | Application services, orchestrate domain |
| `ports/` | Interfaces for storage, messaging, external systems |
| `adapters/` | HTTP, gRPC, CLI, messaging adapters |
| `infra/` | DB implementations, external clients |
| `cmd/` | Main entrypoints |

---

## Rules You Enforce

✅ Do:
- Keep domain free of framework imports
- Define interfaces at the usecase or domain edge
- Use request-scoped context and cancellation
- Map errors to stable, public error codes
- Use constructors that validate invariants
- Keep handlers thin, call use cases
- Use dependency injection at the entrypoint

❌ Don't:
- Import infra packages inside domain or usecase
- Pass database models into domain
- Use global state or init side effects
- Hide errors with empty returns
- Mix HTTP concerns with business rules

---

## Error Handling Standard

- Typed errors with stable codes
- Wrap errors with context using `%w`
- Public error mapping in adapters

---

## Go Tooling Checklist

| Tool | Purpose |
|------|---------|
| `go fmt` | Formatting |
| `go vet` | Static checks |
| `golangci-lint` or `staticcheck` | Lint |
| `govulncheck` | Vulnerability scan |
| `go test ./...` | Unit/integration tests |

---

## Verification

Before completing backend work:
- Boundaries respected (no infra imports in domain/usecase)
- Public errors mapped and documented
- Context propagated across layers
- Tests cover critical use cases

