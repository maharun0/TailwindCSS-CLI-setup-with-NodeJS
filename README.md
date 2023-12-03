# TailwindCSS-CLI-setup-with-NodeJS
<i>(Note: This setup is super short. Read official docs for better understandings.)</i>
<br><br>

> [!TIP]
> Open the termianl and copy-paste.

<br>

###### Prerequisites:
 - Make sure you have NodeJS installed.
 - To check Node version:
	```
	node -v
	```
   Output should be like: `v21.3.0`

## Step 1
- Initialize a NodeJs Project.
- Install TailwindCSS with developer dependency.
- Create configuration file for TailwindCSS.
	```
	npm init -y
	npm i -D tailwindcss
	npx tailwindcss init
	```

## Step 2
- Create a folder named `src` and `tailwind.css` file within it having some content.
- Create a folder named `output`.
- Create a folder name `.vscode` and `settings.json` file within it having some content.
	```
	mkdir src
	cd ./src
	echo '@tailwind base;
	@tailwind components;
	@tailwind utilities;' > tailwind.css
	cd ..
	
	mkdir output
	
	mkdir .vscode
	cd ./.vscode
	echo '{
	  "css.validate": false,
	  "tailwindCSS.emmetCompletions": true
	}' > settings.json
	cd ..
	```
## Step 3
- Open `package.json` file.
- Replace 'scripts' section with this section:
  ```
  "scripts": {
    "build": "tailwindcss -i ./src/tailwind.css -o ./output/tailwind.css -w"
  },
  ```
## Step 4
- Open `tailwind.config.js` file.
- Specify `index.html` file's path inside this file.
  (which we will create in next step)
  ```
  content: [
    './index.html' // Specify path of the HTML file
  ],
  ```

## Step 5
- Create `index.html` file in root directory.
  (it has CSS file attached, which will be built during running)
	```
	<!DOCTYPE html>
	<html lang="en">
	  <head>
	    <meta charset="UTF-8" />
	    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
	    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
	    <title>Tailwind Project</title>
	    <link rel="stylesheet" href="./output/tailwind.css" />
	  </head>
	  <body>
	    <div class="w-32 h-32 bg-gray-900 m-12 text-white">
 				I'm Tailwind
 			</div>
	  </body>
	</html>
 	```
  
## Step 6
- Run and generate the vanilla CSS file.
  ```
	npm run build
  ```

### OUTCOME
Open the HTML file in the browser and you can see this beauty:
![image](https://github.com/maharun0/TailwindCSS-CLI-setup-with-NodeJS/assets/97397303/39b9d42c-929b-43df-aa41-e16c89b067af)


  
