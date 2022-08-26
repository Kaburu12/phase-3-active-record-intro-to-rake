namespace :greeting do
  desc 'outputs hello to the terminal'
    task :hello do
      puts "hello from Rake!"
    end
  
    desc 'outputs hola to the terminal'
    task :hola do
      puts "hola de Rake!"
    end
  end

  namespace :db do
    desc 'migrate changes to your database'
    task migrate: :environment do
      Student.create_table
    end
    task :environment do
      require_relative './config/environment'
    end
    desc 'seed the database with some dummy data'
    task seed: :environment do
      require_relative './db/seeds'
    end
  end
# rake console
  desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end
# We'll make this task dependent on our environment task so that the Student class and the database connection load first.
desc "runs the environment dependancies"
task :environment do
  require_relative './config/environment'
end

# Let's check to see that we did in fact successfully migrate and seed our database:
# Student.all