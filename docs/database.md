# Database

This project uses a SQLite 3 (i.e., serverless) database. The database file is `tubely.db`.


## Manually inspecting the database through the CLI
- Run `sqlite3 tubely.db` to open the database. This will change the prompt in the terminal to `sqlite>`. Any SQLite queries can be run on the database. To exit the SQLite CLI, `.exit`.

### Users table
- `select * from users;`: See the users table
