# Telemetry Data

## Collected Data

**Metrics (via prometheus-net)**

* Default HTTP request metrics: request counts, status codes, and latencies.
* Database metrics (e.g., connections, query times).
* Runtime and resource metrics (CPU, memory, etc.).
* Other system and application metrics relevant to observability.

**Logs (via Serilog)**

* All HTTP requests and responses.
* All errors and warnings in the system.
* Database-related logs and other system logs.
* Logs are structured and sent to VictoriaLogs via OTEL protobuf in production.

## Telemetry Toggle

* Metrics are always exposed but can be optionally scraped in local development.
* Logs:

  * Locally: written to file.
  * Production: sent to VictoriaLogs.
* Toggle configured via `appsettings.Production.json` and `appsettings.Development.json`.

**Example logging setup:**

```csharp
if (builder.Environment.IsProduction())
{
    loggerBuilder.WriteTo.OpenTelemetry(
        endpoint: "http://<victoria-logs-server>/insert/opentelemetry/v1/logs",
        protocol: OtlpProtocol.HttpProtobuf
    );
}
```

## Modules Responsible

* **Backend API Controllers** – expose metrics and trigger logging events.
* **Logging Middleware** – formats and sends structured logs via Serilog.
* **VictoriaMetrics / VictoriaLogs** – ingest metrics and logs.
* **Grafana** – visualize metrics and logs, provide dashboards and alerting.
* **Configuration** – environment-specific `appsettings.*.json` files control telemetry toggle for development vs production.
