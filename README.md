# FluDa :: BOM

Bill of Materials (BOM) for FluDa Kit modules. Import this BOM to manage consistent versions across all FluDa dependencies.

## Usage

Add the BOM to your project's `dependencyManagement`:

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>io.github.fludakit</groupId>
            <artifactId>fluda-bom</artifactId>
            <version>1.0.0</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```

Then add FluDa dependencies without specifying versions:

```xml
<dependencies>
    <dependency>
        <groupId>io.github.fludakit</groupId>
        <artifactId>fluda-jdbc-client-core</artifactId>
    </dependency>
    <dependency>
        <groupId>io.github.fludakit</groupId>
        <artifactId>fluda-jdbc-client-cdi</artifactId>
    </dependency>
</dependencies>
```

## Included modules

| Module | Description |
|---|---|
| `fluda-jdbc-client-core` | Fluent JDBC client core |
| `fluda-jdbc-client-config` | MicroProfile Config integration |
| `fluda-jdbc-client-cdi` | CDI extension |

## Building

```bash
mvn clean install
```

## Publishing

### Releases (manual)

To publish a release to Maven Central:

1. Go to GitHub Actions → "Publish to Maven Central"
2. Click "Run workflow"
3. Enter the release version (e.g., `1.0.0`)
4. Enter the next development version (e.g., `1.1.0-SNAPSHOT`)

The workflow will:
- Set the release version
- Commit, tag, and push
- Build with `-P release` (signs artifacts, publishes to Maven Central)
- Bump to the next SNAPSHOT version

## Related repositories

- [fludakit/parent](https://github.com/fludakit/parent) — Parent POM with shared dependencies and plugins.
- [fludakit/sql-init](https://github.com/fludakit/sql-init) — SQL schema initialization for Jakarta EE / CDI.
- [fludakit/jdbc-client](https://github.com/fludakit/jdbc-client) — Fluent JDBC client for Jakarta EE / CDI.
- [fludakit/tx](https://github.com/fludakit/tx) — Transaction support for Jakarta EE / CDI.
- [fludakit/examples](https://github.com/fludakit/examples) — Runnable example applications.
- [fludakit/fludakit.github.io](https://github.com/fludakit/fludakit.github.io) — Reference documentation site.

## License

Apache License, Version 2.0. See [LICENSE](LICENSE).
