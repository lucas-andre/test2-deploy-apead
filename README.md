# SITE APEAD
Repositório do site da Alta Peformance EAD, com design moderno, responsivo e acima de tudo, performático.   

### Tecnologias usadas
O projeto é desenvolvido em html, css (Tailwind + PostCSS) e node.js. O design system e tema Tailwind CSS utilizado é o Apollo, criado pela equipe, visando acelerar o desenvolvimento de qualquer projeto que leve a identidade visual da Alta Performance. 

<br>  
  
## ⚙️ Configuração do zero
Por alguma razão maluca você precisa configurar todo o projeto do zero, essas são as intruções detalhadas de configuração de ambiente de desenvolvimento, com o foco no VS Code.

### Istalando o node.js e Node Package Manager (npm)
Instale o node.js e npm em sua máquina. Caso preciso, use o cmd.

   https://nodejs.org/en/download/
	
### Instalando o Tailwind
Guia de instalação Tailwind + PostCSS, lembre-se de ter o node e npm instalados:

 1. Abra seu VS Code, abra seu terminal cmd e digite:

		npm install -D tailwindcss
		
	Depois:

	    npx tailwindcss init

---
 2. Configure os caminhos de arquivo em ***tailwind.config.js***

		module.exports  =  { 
			content:  ["./src/**/*.{html,js}"], 
			theme:  { 
				extend:  {}, 
			}, 
			plugins:  [], 
		}
	
---

 3. Instale o PostCSS-CLI

	    npm install postcss-cli
	    
4. Instale o Autoprefixer

	   npm install autoprefixer

---
 5. Instale a extensão Post CSS Language Support para o VS Code

	https://marketplace.visualstudio.com/items?itemName=csstools.postcss
	
---
6. Crie pastas para o desenvolvimento:  ***src*** (com seu apollo.css, index.html e arquivos .js dentro) e ***dist***. O arquivo ***dist/apollo-output.css*** é onde o código gerado pelo tailwind vai. 
7. No arquivo ***src/apollo.css*** insira:
	
	    @tailwind base;
	    @tailwind components;
	    @tailwind utilities;


8. Declare o uso do arquivo ***dist/apollo-output.css*** no head de seu html
---
9. Inicie o processo de build do Tailwind CLI

		npx tailwindcss -i ./src/apollo.css -o ./dist/apollo-output.css --watch


### Alternativa: 

10. Crie um Script de build no ***package.json***

		"scripts": {
			"build": "postcss src/apollo.css -o dist/apollo-output.css"
		}


12. No terminal rode isso, para iniciar nosso script de build:

		npm run build 


	🎉 **Prontinho! Tudo rodando!**
