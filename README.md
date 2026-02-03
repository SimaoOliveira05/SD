# amazUM

Distributed market analytics and visualization system for sales and statistics, developed for the Distributed Systems course. The application allows exploring metrics about products, sales, users, and market trends with an interactive interface and concurrent operations.

## Grade

**Final Grade:** 18 / 20 ⭐

## Authors

- *Simão Oliveira* -> [@SimaoOliveira05](https://github.com/SimaoOliveira05)
- *Gabriel Dantas* -> [@gabil88](https://github.com/gabil88)
- *José Fernandes* -> [@JoseLourencoFernandes](https://github.com/JoseLourencoFernandes)
- *Luis Ferreira* -> [@1Plus0NE](https://github.com/1Plus0NE)

## Requirements

- Java 17+
- Maven
- Bash (for menu script)

## Building and Running

The project includes a convenient menu script that handles compilation and execution:

```bash
./menu.sh
```

This will present an interactive menu with the following options:
- **Compile** - Builds the project using Maven
- **Run Server** - Starts the server (listens on port `12345` by default)
- **Run Client** - Starts a client instance with interactive UI
- **Run Stress Test** - Launches ChaosMonkey for load testing
- **Clean** - Cleans build artifacts

## Manual Execution

If you prefer to run commands manually:

```bash
# Build the project
mvn clean package

# Start the server
java -cp target/amazUM-1.0.jar org.Server.Server

# Start a client
java -cp target/amazUM-1.0.jar org.Client.ClientUI

# Run stress test
java -cp target/amazUM-1.0.jar org.ChaosMonkey <duration_seconds> <num_threads>
```

## Testing

The included ChaosMonkey stress test tool allows you to simulate concurrent client load:

```bash
# Example: 60 seconds with 20 concurrent clients
java -cp target/amazUM-1.0.jar org.ChaosMonkey 60 20
```

Recommended test scenarios:
- **Light Load:** `60 5` (60s, 5 clients)
- **Normal Load:** `120 20` (120s, 20 clients)
- **Stress Test:** `180 100` (180s, 100 clients)
