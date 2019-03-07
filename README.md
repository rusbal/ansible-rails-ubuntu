# Deploy Rails app on Ubuntu using Ansible

## Steps:

1. ### Bootstrap

   - Install Python version 2

2. ### Create Linux user for app

   - Create user with no password.  No password means this user cannot be used to ssh into the server.

3. ### Install dependencies

   - Install nginx
   - Install postgresql
   - Install node
   - Install ruby
     - Install rbenv to manage ruby version
     - Install ruby
   - Install tree command (Optional: just for easier viewing of installed files)
   - Install build-essential
   - Install certbot for Let's encrypt SSL
   - Install yarn
     - Add an Apt signing key
     - Add Yarn repository
     - Install Yarn

4. ### Prepare environment

   - Create application directory structure
   - Lock the ruby version for the app
   - Set RAILS_ENV=production
   - Install the master key
   - Install gcc compiler
   - Grant sudo rights for app user to manage the application service
   - Configure log rotation for the app
   - Setup non-secure vhost to nginx
   - Setup database
     - Copy database configuration
     - Install PostgreSQL development headers
     - Create app database
     - Create app database user
   - Setup application server
     - Install puma
     - Setup puma configuration
     - Install puma service
     - Enable puma service

5. ### Install Rails application

   - Remove old codebase
   - Clone codebase
   - Install bundle
   - Symlink files to shared directory
     - config/database.yml
     - config/master.key
     - config/puma.rb
     - log
     - tmp
   - Load database schema
   - Precompile assets

6. ### Install SSL certificate

   - Generate certificate using certbot
   - Setup secure vhost

   
