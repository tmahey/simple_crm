# Simple CRM

A Ruby on Rails CRM application using ActiveAdmin, ActiveStorage, and Bulma CSS.

**GitHub Repository:** [https://github.com/tmahey/simple_crm](https://github.com/tmahey/simple_crm)

## Setup Rails

1. Create the Rails app and enter the project folder:
```bash
rails new simple_crm
cd simple_crm
```

2. Generate the `Customer` model and migrate the database:
```bash
rails g model Customer full_name:string phone_number:string email_address:string notes:text
rails db:migrate
```

3. Install ActiveStorage for customer image uploads:
```bash
rails active_storage:install
rails db:migrate
```

4. Add `devise`, `activeadmin`, and `sassc-rails` to `Gemfile`, then install and set up ActiveAdmin:
```bash
bundle add devise activeadmin sassc-rails
rails g active_admin:install
rails db:migrate
rails db:seed
```

5. Register the `Customer` model with ActiveAdmin:
```bash
rails g active_admin:resource Customer
```

6. Start the server and add at least 5 customers at `http://127.0.0.1:3000/admin` (`admin@example.com` / `password`):
```bash
rails s
```

7. Commit and push the initial setup to GitHub:
```bash
git init
git add .
git commit -m "Initial Rails setup with Customer model, ActiveStorage, and ActiveAdmin"
git branch -M main
git remote add origin https://github.com/tmahey/simple_crm.git
git push -u origin main
```

## Part 1 - Customer Partial

1. Create the customer partial file:
```bash
mkdir -p app/views/customers
touch app/views/customers/_customer.html.erb
```

2. Commit and push Part 1 to GitHub:
```bash
git add .
git commit -m "Add customer partial with Bulma styling and image_tag"
git push
```

## Part 2 - Customers Controller, Views, and Routes

1. Generate the `Customers` controller with the three required actions:
```bash
rails g controller customers index alphabetized missing_email
```

2. Commit and push Part 2 to GitHub:
```bash
git add .
git commit -m "Add CustomersController actions, views, and routes"
git push
```

## Run the Project Locally

```bash
git clone https://github.com/tmahey/simple_crm.git
cd simple_crm
bundle install
rails db:migrate
rails db:seed
rails s
```

## Application Routes


All Customers : `http://127.0.0.1:3000/`

Alphabetized Customers : `http://127.0.0.1:3000/customers/alphabetized`
Customers Missing Email : `http://127.0.0.1:3000/customers/missing_email`
ActiveAdmin Dashboard : `http://127.0.0.1:3000/admin` |
