Classes corresponds to =>  Tables

Instances corresponds to => row/record

Define a class
    * Use the singular version of a puralized table name
    *  Capitialized and camel cased
    * Inherit from Active Record Base



    Active_record example:

           Student.create(...)    saves to database automatically

           s = Student.new(...)  create a new instances, but doesn't save until you call the "s.save" method

   
_____  Only retrieves single files!!! _______________

   Student.find(some id)

   Student.find_by( search by attributes/column.names)


   _____ Retrieve multiple files _______________________

   Student.where (attributes/column.names.to_search_by)


   my_student = Student.find(i)


   my_student.update(  )update it in the database

   my_student.first_name = will update the instance but won't update the database until you call "my_student.save"



   my_student.destroy  ex. = Student.destroy(id)

   Student.destroy_alll







