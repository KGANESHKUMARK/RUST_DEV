# My Rust Project

This is a simple Rust project that demonstrates the basic structure of a Rust application.

## Getting Started

To build and run this project, you need to have Rust and Cargo installed on your machine. You can install them by following the instructions at [rust-lang.org](https://www.rust-lang.org/tools/install).

## Building the Project

To build the project, navigate to the project directory and run the following command:

```
cargo build
```

## Running the Application

After building the project, you can run the application using:

```
cargo run
```

## Project Structure

- `src/main.rs`: The entry point of the application.
- `Cargo.toml`: The configuration file for the Cargo package manager.
- `README.md`: Documentation for the project.

## Code coverage
- to install : cargo install cargo-tarpaulin
- cmd : 
```
cargo tarpaulin --out html

cargo tarpaulin --out Xml
```

## # Build the project
```
cargo build --release
```


## run test
```
cargo test
```
## Compilateion mechanism
Cargo, the Rust package manager and build system, handles the compilation and execution of Rust projects. It uses a combination of metadata, dependency management, and build scripts to determine whether it needs to compile the code or if it can simply run the existing binaries. Here's an overview of how Cargo's compilation mechanism works:

How Cargo Determines Whether to Compile
Dependency Graph: Cargo constructs a dependency graph based on the Cargo.toml file. This graph includes all the dependencies and their versions.

Timestamps: Cargo checks the timestamps of the source files and the compiled artifacts. If any source file has been modified since the last compilation, Cargo will recompile the affected parts of the project.

Cargo.lock: Cargo uses the Cargo.lock file to ensure that the exact versions of dependencies are used. If the Cargo.lock file changes (e.g., due to adding or updating dependencies), Cargo will recompile the project.

Build Scripts: If the project or any of its dependencies include build scripts (build.rs), Cargo will run these scripts to determine if any additional compilation steps are needed.

<!-- Compilation Mechanism -->
 <!-- Parsing and Analysis:  -->
Cargo invokes the Rust compiler (rustc) to parse and analyze the source code. This step includes syntax checking, type checking, and borrow checking.

<!-- Intermediate Representation (IR):  -->
The Rust compiler generates an intermediate representation (IR) of the code, which is used for further optimization and code generation.

<!-- Code Generation:  -->
The Rust compiler generates machine code from the IR. This step includes optimizations based on the selected profile (e.g., dev or release).

<!-- Linking:  -->
The generated machine code is linked with the necessary libraries and dependencies to produce the final executable binary.

<!-- Cargo Commands -->
Build: The cargo build command compiles the project. It checks the timestamps and dependency graph to determine if recompilation is needed.

<!-- cargo build -->

Run: The cargo run command compiles the project (if needed) and then runs the resulting binary.

<!-- cargo run -->

Test: The cargo test command compiles the project (if needed) and runs the tests.

<!-- cargo test -->

Clean: The cargo clean command removes the target directory, forcing a full recompilation on the next build.

<!-- cargo clean -->


PostgreSQL:

Why: PostgreSQL is a powerful, open-source relational database known for its advanced features, performance, and scalability. It has strong support in the Rust ecosystem with libraries like sqlx and diesel.
Libraries: sqlx, diesel
Use Cases: Web applications, data warehousing, and complex queries.
MySQL/MariaDB:

Why: MySQL is a widely-used open-source relational database known for its reliability and performance. MariaDB is a fork of MySQL with additional features and improvements.
Libraries: sqlx, diesel
Use Cases: Web applications, e-commerce, and content management systems.
SQLite:

Why: SQLite is a lightweight, serverless, self-contained SQL database engine. It is suitable for smaller applications, prototyping, and applications where simplicity and ease of setup are important.
Libraries: sqlx, rusqlite
Use Cases: Embedded systems, mobile applications, and small to medium-sized applications.
MongoDB:

Why: MongoDB is a popular NoSQL database known for its flexibility, scalability, and ease of use. It is suitable for applications that require a flexible schema and high scalability.
Libraries: mongodb
Use Cases: Real-time analytics, content management, and IoT applications.
Redis:

Why: Redis is an in-memory data structure store used as a database, cache, and message broker. It is known for its high performance and support for various data structures.
Libraries: redis
Use Cases: Caching, real-time analytics, and session management.

sqlx = { version = "0.5", features = ["runtime-tokio-rustls", "postgres", "mysql", "sqlite"] }
--oracle = "0.5"
--odbc = "0.17"
--dotenv = "0.15"

