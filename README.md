# ZigRelate ()

ZigRelate is a database toolkit and Object-Relational Mapping (ORM) library for the Zig programming language. It provides a high-level API for interacting with relational databases, allowing developers to seamlessly integrate database operations into their Zig applications.

## Features

- **Object-Relational Mapping (ORM):** Map Zig structs to database tables for easy and intuitive data manipulation.

- **Database Agnostic:** Designed to work with various relational database management systems (RDBMS) like PostgreSQL, MySQL, SQLite, and more.

- **SQL Expression Language:** Express database queries using Zig constructs, providing a more idiomatic Zig approach to SQL.

- **Connection Pooling:** Efficiently manage and reuse database connections for improved performance.

- **Schema and Data Migration:** Tools for defining and updating database schemas, making it easy to handle changes over time.

## Getting Started

### Installation

```sh
# Clone the repository
git clone https://github.com/yourusername/ZigRelate.git

# Build and install ZigRelate
cd ZigRelate
zig build install
```

### Example Usage

```zig
const std = @import("std");
const ZigRelate = @import("ZigRelate");

const User = struct {
    id: u64,
    name: [const u8] = undefined,
    age: u32,
};

pub fn main() void {
    const db = try ZigRelate.open("sqlite::memory:");

    // Define a table
    const usersTable = db.table(User, "users");

    // Insert a user
    const newUser = User{id: 1, name: "John Doe", age: 30};
    const insertedUser = usersTable.insert(newUser);
    std.debug.print("Inserted user: {d}\n", .{insertedUser.id});

    // Query users
    const queryResult = usersTable.query().filter(.name == "John Doe").execute();
    std.debug.print("Query result: {d}\n", .{queryResult});
}
```

## Documentation

For detailed documentation and examples, please refer to the [Wiki](https://github.com/yourusername/ZigRelate/wiki).

## Contributing

We welcome contributions! Please check out the [Contribution Guidelines](CONTRIBUTING.md) for more details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.