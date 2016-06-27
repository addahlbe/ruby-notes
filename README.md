# ruby-notes

1. start by making the controller:

	$ bin/rails generate controller
	Usage: rails generate controller NAME [action action] [options]
	 
	...
	...
	 
	Description:
	    ...
	 
	    To create a controller within a module, specify the controller name as a path like 'parent_module/controller_name'.
	 
	    ...
	 
	Example:
	    `rails generate controller CreditCards open debit credit close`
	 
	    Credit card controller with URLs like /credit_cards/debit -> /credit_cards/credit -> /credit_cards/close
	    (If you don't specify actions it creates default CRUD actions (Ex. Create, update, delete, index -> you can google these)
	    It will create:
	        Controller: app/controllers/credit_cards_controller.rb
	        Test:       test/controllers/credit_cards_controller_test.rb
	    You will want to create (Possibly)
	        Views:      app/views/credit_cards/debit.html.erb [...]
	        Helper:     app/helpers/credit_cards_helper.rb
        
2. Generate your model: your DB is generated off of the model. Your db keys are generated based off of active record associations (has_many etc: http://guides.rubyonrails.org/association_basics.html)

	$ bin/rails generate model
	Usage:
	  rails generate model NAME [field[:type][:index] field[:type][:index]] [options]
	 
	 ex. bin/rails generate model CreditCard type:String name:string number:integer etc:etc
	 
	...
	 
	Active Record options:
	      [--migration]            # Indicates when to generate migration
	                               # Default: true
	 
	...
	 
	Description:
	    Create rails files for model generator.
    

3. After creating your model, you need to run the db changes:

	$ bin/rake db:migrate
	
4. Make sure your routes are set up properly

5. Implement whatever actions you created for your controller
	ex. def credit
		  	// debit code here, anything you want to use on html page use @variableName 
		  end
			def debit
				// credit code here, anything you want to use on html page use @variableName 
			end
			def close
				// close account code here, anything you want to use on html page use @variableName 
			end
