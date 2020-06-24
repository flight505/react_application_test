## Created deploy a React app on within pages and copy the url
### Let's start by creating a new repo:
Go to github.com/new.
For Repository Name, you can choose any name of your choice, but in this guide, we will be using test-react-gh-pages.
Click Create Repository.

### Next creating the react application 
Open up your terminal and type the following command:

    npx create-react-app test-react-gh-pages

This will create a new folder named test-react-gh-pages (or whatever you named your app). 
Then follow the instructions on how to start and run the application.
Navigate to the folder that was just created.

    cd /path/to/test-react-gh-pages

Link and push your newly created project to Github Repository.

    git init
    git add .
    git commit -m "first commit"
    git remote add origin git@github.com:username/guide-react-gh-pages.git
	git push -u origin master

### Push to Github
Still in the terminal and in the folder for your app, follow these steps:

Install the gh-pages as a dev-dependency

	npm install gh-pages --save-dev

Open the app's packaage.json file and 
Add an homepage field with its value to be the string:

    http://{username}.github.io/{repo-name}, where {username}
 is your GitHub username, and {repo-name} is the name of the GitHub repository you created in Step 1.

    "homepage": "https://myusername.github.io/guide-react-gh-pages",

If you skip the step, the app will not deploy correctly because create-react-app uses the homepage field to determine the root URL in the built HTML file.
Update the existing scripts field with the following:

    "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build"
    },

### Deploy the app.
    npm run deploy
The predeploy script will run automatically before deploy is run.
Voila! The app is now accessible at the URL you specified in the homepage field in the package.json file.

#### Summary
This guide has provided a walkthrough on how you can publish your React application to gh-pages with a few easy steps using create-react-app and gh-pages npm package.
Here is a useful link if you'd like to learn more:
* [Facebook tutorial](https://create-react-app.dev/docs/deployment/#github-pages-https-pagesgithubcom)




This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `npm run build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
