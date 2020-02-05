require 'pry'
#namespace is essentially the grouping of tasks under a specified name
namespace :greeting do

  #desc is what shows up after you type rake --tasks in terminal
  desc 'outputs hello to the terminal'

  #create method called :hello, under greeting namespace  
  task :hello do 
      
      #this will only output if we type into terminal: `rake greeting:hello`
      puts "hello from Rake!"
    end
  
  #this is essentially a repeat of above, w/ different desc, tasks and output
  desc 'outputs hola to the terminal'
    task :hola do
      puts "hola de Rake!"
    end
  end

task :environment do
  require_relative './config/environment'
end

namespace :db do
  desc 'migrate changes to your database'
  task :seed do
    require_relative './db/seeds.rb'
  end
  task :migrate => :environment do
    Student.create_table
  end
end

desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end