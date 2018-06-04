Classes corresponds to =>  Tables

Instances corresponds to => row/record

Define a class
    *  Use the singular version of a puralized table name
    *  Capitialized and camel cased
    *  Inherit from Active Record Base


    Active_record example:
           Student.create(...)    saves to database automatically
           s = Student.new(...)  create a new instances, but doesn't save until you call the "s.save" method

   
_____  Only retrieves single files!!! _______________

   Student.find(some id)

   Student.find_by( search by attributes/column.names)


_____    Retrieve multiple files _______________________

   Student.where (attributes/column.names.to_search_by)


   my_student = Student.find(i)



   my_student.update(  )update it in the database

   my_student.first_name = will update the instance but won't update the database until you call "my_student.save"


_____________ D E S T R O Y _________________

   my_student.destroy  ex. = Student.destroy(id)

   Student.destroy_all

   ____________ Relationships  __________

        *** One to One ***
"belongs_to" is always singular.

"has_one"  is always singular, as well.  If the "id" exisits in another table, then the other table gets "has_one" 


           *** One to Many ***
"has_many" is plural

"belongs_to"  is singular.

     *** Many to Many ***

     - You need 3 tables!
       _ first define the relationship with join table.
        - Then define the relationship with the target table through the join table.


________  Rake Stuff ____________________

1) to create a rake migration
     - rake db:create_migration NAME=something_something

          -this will create a new file, go to that file, dummy.  Check your "db/migrate/" folder.

2)   create a table:
            ex.
                def change
                  create_table :todos do |t|
                    t.string :name
                    t.string :description
                  end
                end



 3) to add stuff
     - rake db:migrate

    to undo (ctrl -z)
     - rake db:rollback


****************    H E R O K U     ***********

   heroku -V  tells you the version installed.


   Make sure you have these 2 things done:
     1) add "config.ru" file, then add this:
         "
         require'./app'
         run Sinatra::Application
         "
      2) in "database.yml" add:
      "
                production:
                <<: *defaults
                url: ENV['DATABASE_URL']
      "


 the launch a site on Heroku, on terminal:
   0) hekro login.
   1) git add.
   2) git commit -m" somethin somethin".
   3) git status (not needed, but should see 'nothing to commit, working tree clean.').
   4) git push heroku master.
   5) heroku open - opens application.
   6) heroku run rake db:migrate - do this to add tables made.
   7) heroku console  - it's like RUBY's IRB, it is a virtual enviroment.
   8) heroku restart - to restart heroku server.
   9) heroku logs -t   --- gives you a log of all inputs.


On the HEROKU profile  
  
   in 'settings', find 'Config Vars'
      add 'SEI_SESSIONS_SECRET'( it is in the app.rb file)
        then give it a super long, random number string, up to like 20 characters.

  - heroku logout --  to...um, log out.

  - heroku destroy,  as in gone for good.
















