Cuál sería la manera correcta de agregar tecnología JWT para este implementando Arquitectura hexagonal y DDD dentro del frontend, se alinea a buenas practicas de DDD y arquitectura hexagonal y codigo escalable, mantenible y testeable.


Puntos clave
- app (todo lo necesario para arrancar la app)
	- main
		- io
			- santiagovogit
				- carwashmetro
					- MainApplication 
		- resources
			- application.properties
	- test
		- io
			- santiagovogit
				- carwashmetro
	- build.grandle
- src
	- bounded-context (depende de shared)
		- main
			- io
				- santiagovogit
					- carwashmetro
						- domain
							- clases java
						- infrastructure
							- clases java
						- application
							- clases java
		- test
		- - build.grandle
	- shared (recursos comunes para bounded context)
		- main
			- io
				- santiagovogit
					- carwashmetro
						- domain
							- clases java
						- infrastructure
							- clases java
		- test
		- - build.grandle

# Hexagonal Spring Skeleton  
Template for a Spring application with hexagonal architecture + DDD focused on REST API  
  
## Prerequisites  
- Java SE 17  
- Deployed PostgreSQL database  
  
### Installation with CLI:  
- Build the project using Gradle  
    - `./gradlew build`  
  
- Configure environment variables in `application.properties`  
    - `${DATASOURCE_URL}`  
    - `${DATASOURCE_USERNAME}`  
    - `${DATASOURCE_PASSWORD}`  
  
- Run the application:  
    - `./gradlew bootRun`

spring.datasource.url=jdbc:postgresql://aws-0-us-east-1.pooler.supabase.com:6543/postgres  
spring.datasource.username=postgres.inrkdquzxxkgourngwef  
spring.datasource.password=Valenciano2005.