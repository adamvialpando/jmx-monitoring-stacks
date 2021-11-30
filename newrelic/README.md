# New Relic 

## Prerequsite 

[Create a New Relic account](https://newrelic.com/signup)

## Installation

To install the Java agent you need to configure your JVM to load the agent during your application's `premain` start-up by passing the `-javaagent:/full/path/to/newrelic.jar` command-line argument. This process varies depending on your environment/application server.

In this demonstration the following nodes of cp-demo are configured with this agent: `zookeeper`, `kafka1`, `kafka2`, `streams-demo`, `connect`, `schemaregistry`, `ksqldb-server` and `restproxy` using the configuration in `docker-compose.override.yml`.

For full details see:
- [General installation instructions](https://docs.newrelic.com/docs/agents/java-agent/installation/install-java-agent)
- [Application server specific instructions](https://docs.newrelic.com/docs/agents/java-agent/installation/include-java-agent-jvm-argument)
- [Additional installation instructions (Maven, Gradle, etc)](https://docs.newrelic.com/docs/agents/java-agent/additional-installation)

## Getting started

See the [getting started guide](https://docs.newrelic.com/docs/apm/agents/java-agent/getting-started/introduction-new-relic-java/) as well as the [compatibility and requirements documentation](https://docs.newrelic.com/docs/agents/java-agent/getting-started/compatibility-requirements-java-agent) for an overview of what is supported by the Java agent.

- Rename `newrelic.yml.sample` to `newrelic.yml`
- Update `newrelic.yml` with your new relic license key. 
    ```yml
      license_key: 'your license key here'
    ```
    Your license key is an API key in your New Relic account. It is of `type`: `INGEST - LICENSE`, its name is `License Key for [Your Account Name]` and the notes should say `Original account license key`. You can find it in -and copy it from- the API Keys section in your New Relic account.

    ```yml
      app_name: 'your application name here'
    ```
    You application name -as configured in the `newrelic.yml` configuration file- is the name under which your data will be collected in your New Relic account. Use this config to group data from diparate nodes (i.e. newrelic agents).

After these steps the steps to starting this demo are similar to [the instructions](../README.md) for other demos in this repository.
