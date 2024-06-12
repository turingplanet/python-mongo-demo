# Python MongoDB Connection Demo
This project demonstrates how to connect Python3 with MongoDB and provides examples of parsing stock information and storing it in the database.

## Prerequisites
Before running the project, make sure you have the following:
- Python 3 installed
- Poetry package manager installed
- MongoDB installed and running

## MongoDB Setup
To set up MongoDB on Mac, please refer to the official MongoDB documentation: [Install MongoDB on macOS](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-os-x/)

Here are some sample commands to start and stop MongoDB locally:
```shell
# Start MongoDB
$ brew services start mongodb-community@7.0

# Stop MongoDB
$ brew services stop mongodb-community@7.0
```

## Poetry Setup
This project uses Poetry for dependency management. Please refer to the [Poetry Project Setup](https://github.com/turingplanet/python-project-setup-tutorial/blob/main/comprehensive_set_up.md#poetry-project-setup) section in the Python Project Setup Tutorial for instructions on how to set up Poetry.

Install the project dependencies using Poetry:
```shell
git clone <repository_url>
cd <project_directory>
poetry install
```

## Project Structure
- `mongo_demo`: Contains the modules for simple MongoDB connection.
- `stock_info_parser`: Contains modules to grab stock information and store it in MongoDB.

## Running the Project
### Using Alpha Vantage API
To use the Alpha Vantage API for parsing stock data, follow these steps:
1. Obtain an API key from Alpha Vantage.
2. Set the `API_KEY` in the `secret.yml` file.
3. Run the following command:
   ```shell
   poetry run python3 run stock_info_parser/pipeline.py
   ```

### Using Public CSV Data
Alternatively, you can use public CSV data to load stock information. Follow these steps:
1. Run the following command to grab data from GitHub:
   ```shell
   poetry run python3 run stock_info_parser/github_pipeline.py
   ```

## MongoDB Atlas

If you want to use MongoDB Atlas instead of a local MongoDB instance, you need to change the `MONGO_URI` in the `secret.yml` file to the following format:

```
mongodb+srv://xxxxxx@xxxx.xxxxx.mongodb.net/xxxx?retryWrites=true&w=majority
```

Replace `xxxxxx` with your MongoDB Atlas credentials and database information.

## Additional Resources

- [MongoDB Documentation](https://docs.mongodb.com/)
- [PyMongo Documentation](https://pymongo.readthedocs.io/)
- [Alpha Vantage API Documentation](https://www.alphavantage.co/documentation/)

Happy coding!

