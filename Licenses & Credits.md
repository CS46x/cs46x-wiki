_Owner: Team | Last updated: 2026-03-09 | Status: Draft_

# Licenses & Credits

## Purpose
Third-party dependencies, licenses, and attributions for all ArenaRaid repositories.

---

## Project License

This project is released under the **MIT License**.

---

## Third-Party Dependencies

### Frontend - `cs46x-frontend-app`

- **@angular/** v21 (MIT) - Core Angular framework: components, routing, forms, animations, and browser platform
- **@microsoft/signalr** v9.0.6 (MIT) - SignalR client library used to connect to the real-time server hubs (`/chat`, `/messengerhub`)
- **bootstrap** v5.3.8 (MIT) - CSS utility and component framework used for UI layout and styling
- **mediasoup-client** v3.3.17 (ISC) - WebRTC client for the SFU (Selective Forwarding Unit) voice/video transport layer
- **rxjs** v7.8.0 (Apache-2.0) - Reactive extensions for JavaScript; used throughout Angular for async streams and event handling
- **socket.io / socket.io-client** v2.x (MIT) - WebSocket library
- **toastr** v2.1.4 (MIT) - Toast notification library for in-app alerts and feedback messages
- **zone.js** v0.15 (MIT) - Angular's async change-detection layer
- **tslib** (0BSD) - TypeScript runtime helper library

### Realtime Service - `cs46x-realtime-service`

- **AutoMapper** v14.0.0 (MIT) - Object-to-object mapping between entity classes and API/hub models
- **AWSSDK.SimpleEmail** v4.0.2 (Apache-2.0) - AWS SES client used to send password reset and notification emails
- **Microsoft.AspNetCore.Authentication.JwtBearer** v8.0.21 (MIT) - JWT bearer token authentication middleware
- **Microsoft.AspNetCore.DataProtection.EntityFrameworkCore** v8.0.21 (MIT) - Persists ASP.NET Data Protection keys to MySQL
- **Microsoft.AspNetCore.Identity.EntityFrameworkCore** v8.0.21 (MIT) - ASP.NET Core Identity backed by EF Core
- **Microsoft.AspNetCore.SignalR.StackExchangeRedis** v8.0.23 (MIT) - Redis backplane for SignalR, enabling hub message distribution across multiple server instances
- **Microsoft.EntityFrameworkCore.Design** v8.0.0 (MIT) - EF Core design-time tools used for `dotnet ef migrations`
- **Pomelo.EntityFrameworkCore.MySql** v8.0.3 (MIT) - EF Core provider for MySQL/MariaDB
- **StackExchange.Redis.Extensions.AspNetCore/Core/Newtonsoft** v11.0.0 (MIT) - Redis client extensions for ASP.NET Core
- **Swashbuckle.AspNetCore** v6.6.2 (MIT) - Swagger/OpenAPI documentation UI at `/swagger`
- **Microsoft.VisualStudio.Azure.Containers.Tools.Targets** v1.21.0 (MIT) - Docker integration tooling for visual studio

### Infrastructure - `cs46x-frontend-app/cdk` & `cs46x-redis-backend/infrastructure`

- **aws-cdk-lib** v2.x (Apache-2.0) - AWS Cloud Development Kit
- **constructs** v10.x (Apache-2.0) - Base programming model for CDK constructs
- **aws-cdk** v2.x (Apache-2.0) - CDK CLI used to synthesize and deploy CloudFormation stacks.
- **ts-node / typescript** (MIT / Apache-2.0) - TypeScript compilation for CDK and test code
- **jest / ts-jest** (MIT) - Unit testing framework used for CDK stack tests.

---

## Credits / Attributions

- Initial Angular frontend application scaffolding by **Scott** (team member).
- GenAI tools (OpenAI ChatGPT, Github Copilot) used for development assistance - see [GenAI Usage Log](GenAI-Usage-Log-&-Citations) for full entries.
- AWS SDK and CDK documentation referenced throughout infrastructure setup.

