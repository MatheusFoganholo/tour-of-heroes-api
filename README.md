# tour-of-heroes-api 🦸‍♂️

Repository created to store a simple project I did following the @peimelo Rails 6 course.
<br/>
This project is an API made with Rails to take a tour of your registered heroes. Each user who enters the application will have their own heroes, according to the token provided in the header.

<table>
  <tr>
    <td>Ruby version</td>
    <td>
      3.0.1
    </td>
  </tr>
  <tr>
    <td>Rails version</td>
    <td>
      6.1.x
    </td>
  </tr>
  <tr>
    <td>Database</td>
    <td>
      SQLite3 (dev) / PostgreSQL (prod)
    </td>
  </tr>
</table>

## Initial settings to run the project

```bash
# Clone the project
git clone https://github.com/MatheusFoganholo/tour-of-heroes-api.git

# Enter the cloned directory
cd tour-of-heroes-api

# Install Ruby on Rails dependencies
bundle install

# Create the development and test databases
rails db:create

# Create the tables
rails db:migrate

# Run the project
rails s
```

The backend will be available at `http://localhost:3000`.

## Using the Heroes API

### Include a Header Authorization

For all requests, use an **Authorization header**, of size> = 10 characters, so that you can only manipulate your data, for example:

```bash
curl --request GET \
  --url 'https://api-tour-of-heroes.herokuapp.com/api/heroes' \
  --header 'Authorization: anyTokenCanBeUsed'
```

### API Endpoint

The following endpoints are available:

| Endpoints                   | Usage                                     | Params             |
| --------------------------- | ----------------------------------------- | ------------------ |
| `GET /api/heroes`           | Get all of the heroes.                    |                    |
| `GET /api/heroes?name=term` | Get all heroes with `name` like a `term`. | **term**: [String] |
| `GET /api/heroes/:id`       | Get the details of a single hero.         |                    |
| `POST /api/heroes`          | Add a new hero.                           | **name**: [String] |
| `PUT /api/heroes/:id`       | Edit the details of an existing hero.     | **name**: [String] |
| `DELETE /api/heroes/:id`    | Remove the hero.                          |                    |
