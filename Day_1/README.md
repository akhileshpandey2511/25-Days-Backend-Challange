## Day_2: How to deploye Backend Code in Production

A JavaScript-based backend utilizes Node.js to handle server-side operations. Data management involves storing and retrieving information, often employing databases like MongoDB or MySQL. File handling involves processing uploads, downloads, and storage. Integrating third-party APIs allows access to external services for functionalities like payment processing or social media interactions. This architecture offers flexibility and scalability, leveraging JavaScript's versatility across the entire web stack. With Node.js, developers can create efficient, real-time applications, making JavaScript a compelling choice for both frontend and backend development, streamlining development workflows and enhancing overall productivity.

 - ** Data
 - ** File
 - ** Third Party(API)
   
-> Javascript Runtime:	Nodejs/Deno/Ban
	Package.json		.env	(Readme,git,lint,prettier etc.)

->	src
	index or main(DB connects)		APP(config,cookie)		constants(enums,DB-name)
	-> DB
	-> Models
	-> Controllers
	-> Routes
	-> Middlewares
	-> Utils
