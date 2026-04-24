# AGW Federated GitOps -- Cluster 2 (Leaf-2)

Developer self-service repository for leaf-2 (cluster3) in the [AGW Federated GitOps Reference Architecture](https://github.com/ably77/agentgateway-federated-gitops-ref-arch).

## What Developers Can Do

- **Routes**: HTTPRoute, GRPCRoute for AI traffic routing
- **Services**: Deploy workloads in team namespaces
- **Policies**: Namespace-scoped timeouts, retries, headers
- **ReferenceGrants**: Cross-namespace backend references

## What Developers Cannot Do

- Create or modify AgentgatewayBackend (blocked by Kyverno)
- Override global guardrail policies (blocked by Kyverno)
- Modify admission policies or RBAC (blocked by Kubernetes RBAC)

## Structure

```
team-enrollment/
├── services/     # Deployments, Services, ServiceAccounts
├── routes/       # HTTPRoutes, ReferenceGrants
└── policies/     # Namespace-scoped RBAC
```

## Related Repos

- [agw-federated-infra](https://github.com/ably77/agw-federated-infra) -- Platform infrastructure
- [agw-federated-cluster-1](https://github.com/ably77/agw-federated-cluster-1) -- Leaf-1 workloads
