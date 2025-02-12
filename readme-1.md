## Setting Up Tailwind CSS with Django

### Prerequisites
Ensure you have the following installed:
- Node.js and npm
- Django

### Installation Steps

#### 1. Initialize npm in the Root Directory
Run the following command in your project's root directory(myproject-the folder which you created for cloning thee project):
```sh
npm init -y
```

#### 2. Install Tailwind CSS and Dependencies
Install Tailwind CSS, PostCSS, and Autoprefixer:
```sh
npm install -D tailwindcss postcss autoprefixer
```

#### 3. Initialize Tailwind CSS
Generate the `tailwind.config.js` file:
```sh
npx tailwindcss init
```

#### 4. Configure Tailwind Content Paths
Update `tailwind.config.js` to include the following:
```js
module.exports = {
  content: [
    './website/home/templates/**/*.html',
    './website/static/js/**/*.js',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

#### 5. Create a Tailwind CSS File
Inside your static CSS folder, create `tailwind.css` and add:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### 6. Configure Build Script in `package.json`
Add the following inside the `scripts` section:
```json
"build:css": "npx tailwindcss -i ./static/css/tailwind.css -o ./static/css/output.css --watch"
```

#### 7. Build Tailwind CSS
Run the following command to build the CSS:
```sh
npm run build:css
```

#### 8. Run Django Normally
After compiling Tailwind, run your Django project as usual:
```sh
python manage.py runserver
```

### Notes
- Ensure `output.css` is included in your Django templates.
- Restart the build process if you make changes to `tailwind.css`.

You're all set! 🚀

