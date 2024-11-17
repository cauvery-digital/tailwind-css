
Install Tailwind via npm
For most projects (and to take advantage of Tailwind’s customization features), you’ll want to install Tailwind and its peer-dependencies via npm.

https://tailwindcss.com/docs/installation
npm init
npm install -D tailwindcss@latest postcss@latest autoprefixer@latest

npm install -D tailwindcss
npx tailwindcss init

Configure your template paths
Add the paths to all of your template files in your tailwind.config.js file.

/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}

Add the Tailwind directives to your CSS
Add the @tailwind directives for each of Tailwind’s layers to your main CSS file.

src/input.css

@tailwind base;
@tailwind components;
@tailwind utilities;


npx tailwindcss -i ./src/input.css -o ./public/assets/css/output.css --watch

Start using Tailwind in your HTML
Add your compiled CSS file to the <head> and start using Tailwind’s utility classes to style your content.

<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="./output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</body>
</html>