# React.js Demo

### Description

This is a React.js/Next.js based landing page plug-n-play template, ideal for startups/companies/service providers wanting to showcase their vision in a single page sleek and modern landing page.

### Features

- 📱  Responsive design

- 🔥 [Next.js](https://nextjs.org) for Static Site Generator

- 🎨 Integrate with [Tailwind CSS](https://tailwindcss.com) (w/ JIT mode)

- 💅 PostCSS for processing Tailwind CSS and integrated to `styled-jsx`

- 🎉 Type checking [TypeScript](https://www.typescriptlang.org)

- 🗂 VSCode configuration: Debug, Settings, Tasks and extension for PostCSS, ESLint, Prettier, TypeScript

- 🤖 SEO metadata, JSON-LD and Open Graph tags with Next SEO

- 🖱️ One click deployment with Vercel or Netlify (or manual deployment to any hosting services)

Built-in feature from Next.js:

- ☕ Minify HTML & CSS
- 💨 Live reload
- ✅ Cache busting

### CI/CD architecture

Platform: Github Actions

The pipeline is triggered by a push commit in `develop` branch. This includes the PRs merged into the branch. `develop` branch is a protected branch also known as the integration branch. All feature branches should be checked out and merged back from `develop` branch after being tested and approved by the relevent code owners. As the frontend is pretty straightforward and does not contain any unit tests at the moment, CI/CD setup performs the following steps:

- Checkout repository
- Sets up Node version 16
- Installs dependencies (Also cache them)
- Builds application
- Configures AWS credentials
- Deploys the application on S3

The steps are dependent on each other so if for example a step fails for whatever reason, all the next steps will be skipped. This protects against several problems including deploying corrupted code.


### Setup Instructions
#### 1. Clone repo

```
git clone https://github.com/Abdullahxz/frontend-azm.git
cd frontend-azm
yarn
```

Then, you can run locally in development mode with live reload:

```
yarn dev
```

Open <http://localhost:3000> with your favorite browser to see your project.

#### 2. Add your own content

 1. **Content**: change the configuration in the ```src/config/index.json``` file to change the content of the landing page to match your use ```src/config/index.json```  folder and .
 2. **Images**:  add any images/icons..etc to the ```public/assets/images```  folder and update their reference source in ```src/config/index.json```.
 3. **Theme**:  to change the theme, update the ```tailwind.config.js```  file to match the theme of your branding. [Tutorial](https://tailwindcss.com/docs/configuration).

##### Deploy manually

You can see the results locally in production mode with:

  ```
yarn build
yarn start
```

The generated HTML and CSS files are minified (built-in feature from Next js). It will also removed unused CSS from [Tailwind CSS](https://tailwindcss.com).

You can create an optimised production build with:

```
yarn build-prod
```

