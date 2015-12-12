# [WEB PROGRAMMING](http://georgeosddev.github.com/markdown-edit)
### Bonadiman Gabriele & Munarini Stefano


Develop a student’s blog where it is possible exchange ideas, school information and educational material. Follow other informations.


## DETAILS

This project was build with JAVA Servlet and JSP using MVC as architectural pattern. The entire project i shouted in GlassFish server v4.0 with Derby database.

## LIBRARIES

JSTL: Allow to manage JSP data without JAVA. accordingly to have html cleaner
GSON: Create and edit JSON objects, used in admin table
JQUERY: Front-end effects 


##DATABASE

Relational Database with minimal structure and few relations.

	UTENTI (id,username,password,email,avatar,tipo_utente,data_time)
	POSTS (id, testo, utente*, gruppo*,date_time,file)
	GRUPPI (id, nome, data_creazione, flag, proprietario*,stato)
	GRUPPIUTENTE(id, utente*, gruppo*)
	INVITI (id,utente*,gruppo*,stato)
	

#ARCHITECTURE

This is the project’s architecture (according to MVC pattern). We decided to use different packages com.secondoProgetto to separate Models, View and Controller each other.

Controller 
		Contains the Servlet files as Controller. These create the Models (Beans) and forward them to the View (JSP Page);

Database
		Contains a single class. From this, we create the connection to the database using  web.xml params

Filters
		Contains  the JavaFilter, mapped on web.xml. These filters are mapped from name, class and url. URL indicates which are the target servlet
		
Listener 
		Contains one class: ContextListener.

Model 
		Contains JAVA classes which mapping all relational data.

Services 
		All the classes used to connect to database method

Servlet 
		Control Servlet. Their role is query database as CRUD service.





##FILTERS

There are four main filters into the project, each with a specific function.

	FILE 		Avoid the non logged user to visit internal page
	GRUPPO	If you are not in the group, you can not access to the material
	MOD	 	If you are not admin, you can not manage groups
	SESSION 	Control if user is logged.
