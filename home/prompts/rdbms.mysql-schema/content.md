# Task
Please generate a MySQL schema for a database containing two tables:
a "person" table and an "address" table.

## Requirements:
- The "person" table should include:
- id (primary key, auto-increment)
- first_name (varchar)
- last_name (varchar)
- email (varchar)
- address_id (foreign key referencing the "address" table)
- The "address" table should include:
- id (primary key, auto-increment)
- street (varchar)
- city (varchar)
- state (varchar)
- zip_code (varchar)
- type (varchar to indicate "live" or "work")

Return your answer as a JSON object with two keys:
- "markdown": A markdown-formatted explanation of the schema design.
- "schema": The SQL statements for creating the schema, as plain text.

## Example Results
{
"markdown": "## MySQL Schema Explanation\n\nThis schema includes two tables... [additional explanation]",
"schema": "CREATE TABLE address (\n  id INT AUTO_INCREMENT PRIMARY KEY,\n  street VARCHAR(255),\n  city VARCHAR(100),\n  state VARCHAR(100),\n  zip_code VARCHAR(20),\n  type VARCHAR(20)\n);\n\nCREATE TABLE person (\n  id INT AUTO_INCREMENT PRIMARY KEY,\n  first_name VARCHAR(100),\n  last_name VARCHAR(100),\n  email VARCHAR(255),\n  address_id INT,\n  FOREIGN KEY (address_id) REFERENCES address(id)\n);"
}

