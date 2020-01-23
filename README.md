# CHEATCHEAT_JPA_SETUP

##Open CMD. Navigate to bin:
	{Drive on computer}\Program Files\PostgreSQL\{version}\bin"
	pg_ctl -D "{Drive on computer}:\Program Files\PostgreSQL\{version}\data" start
##Local server started!


#open pgAdmin => http://127.0.0.1:51711/browser/

	##General
	Servers=>create=>server
	Name: {Descpritive name}
	Servergroup: Servers
	Connect Now: ✅

	##Connection
	Host name/adress: {localhost / descriptive name}
	Port:5432
	Maintanance database: postgres
	Username: {your username, default postgres}
	Password: {your password}
	Save Password: ✅
	##Save

##Create database

  Right-click databases => create=>database
	Database: {database_name}
	Owner: {your username}
	Save


{your_project_folder}/src/main/resources/application.proprerties:

------------------ POSTGRESQL -------------------------------------


	# Web Server settings
	# server.port = 9090
	# ===============================
	# = LOGGING
	# ===============================
	# logging.level.org.springframework = debug
	# ===============================
	# ===============================
	# = DATA SOURCE
	# ===============================
	# Set here configurations for the database connection
	spring.datasource.url=jdbc:postgresql://localhost:5432/{database_name}
	spring.datasource.username=postgres
	spring.datasource.password=root
	spring.datasource.driver-class-name=org.postgresql.Driver
	# Keep the connection alive if idle for a long time (needed in production)
	spring.datasource.testWhileIdle=true
	spring.datasource.validationQuery=SELECT 1
	# ===============================
	# = JPA / HIBERNATE
	# ===============================
	# Show or not log for each sql query
	spring.jpa.show-sql=true
	# Hibernate ddl auto (create, create-drop, update): with "create-drop" the database
	# schema will be automatically created afresh for every start of application
	spring.jpa.hibernate.ddl-auto=create
	# Naming strategy
	spring.jpa.hibernate.naming.implicit-strategy=org.hibernate.boot.model.naming.ImplicitNamingStrategyLegacyHbmImpl
	spring.jpa.hibernate.naming.physical-strategy=org.springframework.boot.orm.jpa.hibernate.SpringPhysicalNamingStrategy
	# Allows Hibernate to generate SQL optimized for a particular DBMS
	spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
	### Settings of Connection pool
	spring.datasource.max-active=50
	spring.datasource.max-idle=8
	spring.datasource.min-idle=8
	spring.datasource.initial-size=10





---------------------- #MYSQL----------------------------------

	# Web Server settings
	# server.port = 9090
	# ===============================
	# = LOGGING
	# ===============================
	# logging.level.org.springframework = debug
	# ===============================
	# Connection url for the database "Local MySQL"
	spring.datasource.url = jdbc:mysql://localhost:3306/database_name?&autoReconnect=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
	# Username and password
	spring.datasource.username = root
	spring.datasource.password = your_password
	# Keep the connection alive if idle for a long time (needed in production)
	spring.datasource.testWhileIdle = true
	spring.datasource.validationQuery = SELECT 1
	# ===============================
	# = JPA / HIBERNATE
	# ===============================
	# Use spring.jpa.properties.* for Hibernate native properties (the prefix is
	# stripped before adding them to the entity manager).
	# Show or not log for each sql query
	spring.jpa.show-sql = true
	# Hibernate ddl auto (create, create-drop, update): with "update" the database
	# schema will be automatically updated accordingly to java entities found in
	# the project. Set to none if its up and running
	spring.jpa.hibernate.ddl-auto = create
	# Naming strategy
	spring.jpa.hibernate.naming-strategy = org.hibernate.cfg.ImprovedNamingStrategy
	# Allows Hibernate to generate SQL optimized for a particular DBMS
	spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQL5Dialect
	### Settings of Connection pool
	spring.datasource.max-active=50
	spring.datasource.max-idle=8
	spring.datasource.min-idle=8
	spring.datasource.initial-size=10



----------------------------- H2 ----------------------------------

	# H2
	spring.h2.console.enabled=true
	spring.h2.console.path=/h2Console
	# Datasource
	spring.datasource.url=jdbc:h2:mem:test
	spring.datasource.username=sa
	spring.datasource.password=
	spring.datasource.driver-class-name=org.h2.Driver
	# Show or not log for each sql query
	spring.jpa.show-sql = true
	# Hibernate ddl auto (create, create-drop, update): with "update" the database
	# schema will be automatically updated accordingly to java entities found in
	# the project. Set to none if its up and running
	spring.jpa.hibernate.ddl-auto = create
	# Naming strategy
	spring.jpa.hibernate.naming-strategy = org.hibernate.cfg.ImprovedNamingStrategy
	# Allows Hibernate to generate SQL optimized for a particular DBMS
	spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.H2Dialect

