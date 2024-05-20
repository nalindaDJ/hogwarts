# Hogwarts

Hogwarts is a bash script designed to execute MySQL scripts across multiple databases listed in a provided file. It's a handy tool for managing database operations efficiently.

## Usage

To use Hogwarts, you need to follow the syntax:

```bash
hogwarts -d <database_list_file> -s <mysql_script_file> [-i <ignore_databases>]
```

Here's a breakdown of each component:

- `-d <database_list_file>`: This file contains a list of databases, each on a separate line. Hogwarts will iterate through these databases and execute the MySQL script against them.
- `-s <mysql_script_file>`: This file contains the MySQL script that you want to execute on the databases listed in `<database_list_file>`.
- `-i <ignore_databases>`: (Optional) A comma-separated list of databases to ignore.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/nalindaDJ/hogwarts.git
```

2. Make the script executable:

```bash
chmod +x hogwarts
```

## Example Usage

Suppose we have a MySQL script named `my_script.sql` that we want to execute across multiple databases listed in `live_dbs.txt`.

The contents of `live_dbs.txt` might look like this:

```
database1
database2
database3
```

And `my_script.sql` might contain SQL commands you want to execute across these databases.

To execute the script using Hogwarts, run the following command:

```bash
./hogwarts -d live_dbs.txt -s my_script.sql
```

Hogwarts will execute `my_script.sql` on each database listed in `live_dbs.txt`. It will log the execution details in a file named `mysql_script_log.txt`.

```bash
./hogwarts -d test_dbs.txt -s my_script.sql
```

Hogwarts will execute `my_script.sql` on each database listed in `test_dbs.txt`. It will log the execution details in a file named `mysql_script_log.txt`.


## Script Features

- Checks the correct number of arguments and provides usage instructions if incorrect.
- Validates the existence of the database list file and MySQL script file.
- Executes the MySQL script for each database listed in the file.
- Logs execution details, including success or failure, to a log file (`mysql_script_log.txt`).

## Configuration

You may need to customize the following variables in the script according to your MySQL setup:

- `MYSQL_USER`: The MySQL user to connect with. Default is `"root"`.
- `MYSQL_PASSWORD`: The password of the MySQL user. Default is `"Password"`.

Ensure you have appropriate permissions and access rights configured in your MySQL setup.

## Conclusion

Hogwarts simplifies the task of executing MySQL scripts across multiple databases, providing convenience and efficiency in managing database operations. With its straightforward usage and robust error handling, it's a valuable addition to any database administrator's toolkit.

## Contribution

Contributions are welcome! Please fork the repository and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

