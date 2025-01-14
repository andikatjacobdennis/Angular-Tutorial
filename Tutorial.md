# Angular Tutorial

## What is Angular?
Angular is a **popular open-source JavaScript/TypeScript framework** developed by Google, designed to make building **dynamic single-page applications (SPAs)** easier.

---

## **Angular: Overview**
- **Purpose**: Facilitates the development of dynamic, interactive SPAs with robust architecture and extensive features.
- **Key Features**:
  - **Two-way Data Binding**: Synchronizes the model and the view.
  - **Dependency Injection**: Simplifies the management of service dependencies.
  - **Component-Based Architecture**: Modularizes the application into reusable components.
  - **Tooling Support**: Seamless integration with tools like Angular CLI.
  - **Community**: Backed by a vibrant developer community offering support and resources.
  - **Integration**: Works well with other libraries and tools.

---

## **Angular CLI**
Angular CLI is a **Command Line Interface tool** that streamlines Angular application development. 

### **Key Benefits**:
- Initialize, scaffold, and maintain Angular projects effortlessly.
- Automates tasks like:
  - Running a development server for live previews.
  - Deploying the application to various environments.
  - Generating components, services, and modules.
  - Running unit tests and end-to-end (E2E) tests.
- Provides mobile app support and robust data security.

---

### **Setting Up Angular CLI**
1. **Prerequisites**:
   - **Node.js**: Install the LTS version from [Node.js Official Website](https://nodejs.org) to ensure stability.
   - Verify installation using:
     ```
     node -v
     npm -v
     ```

2. **Install Angular CLI**:
   Use **npm** (Node Package Manager) to install Angular CLI globally:
   ```
   npm install -g @angular/cli
   ```
   - The `-g` flag ensures global installation for system-wide use.

3. **Verify Installation**:
   Check the installed Angular CLI version:
   ```
   ng version
   ```
   This also displays the versions of Node.js and npm in use.

## **Creating and setting up an Angular project**

### 1. **Creating a New Project**
   - **Command:** `ng new [project-name]`
   - **Options Prompted:**
     - **Angular Routing:** Allows navigation across pages/components in the app. If declined, can be added later.
     - **Stylesheet Format:** Options include CSS, SCSS, SASS, LESS, etc. You chose CSS.

---

### 2. **Project Structure**
   The Angular CLI generates a predefined structure for the project:
   - **`.vscode` folder:** Stores Visual Studio Code settings (e.g., `launch.json` for debugging).
   - **`node_modules` folder:** Contains third-party libraries and dependencies. These are bundled when the app is compiled.
   - **`public` folder:** Contains favicon.ico whic is the browser icon for the app.
   - **`src` folder:** Houses the application source code.
     - **`app` folder:** Contains components and modules, the building blocks of the Angular app.
     - **`assets` folder:** Stores resources like images, icons, and text files.
     - **`index.html`:** The entry point of the application. External styles and scripts are injected dynamically.
     - **`main.ts`:** Bootstraps the Angular app, starting with the `AppModule`.
     - **`styles.css`:** Global styles for the application.
   - **Configuration and Metadata Files:**
     - **`.editorconfig`:** Ensures consistent editor settings across team members.
     - **`.gitignore`:** Specifies files/folders to exclude from version control (e.g., `node_modules`).
     - **`angular.json`:** Project configuration for Angular CLI.
     - **`package.json`:** Defines dependencies and scripts for the project.
     - **`package-lock.json`:** Locks the specific versions of installed dependencies.
     - **`README.md`:** Provides basic documentation for the project.
     - **`tsconfig.*`:** TypeScript configuration files.

---

### 3. **Running the Project**
   - **Command:** `ng serve`
   - **Outcome:**
     - Starts a development server on `http://localhost:4200`.
     - Opens the default browser with the initial Angular app view.

---

### 4. **Introduction to Angular 17**
1. **Server-Side Rendering(SSR)**
what is ssr..
ng new myApp --ssr
2. **new if else**
old example before angular 17
new example
3. **new for**
old example before angular 17
new example
4. **new switch**
old example before angular 17
new example
5. **new switch**
old example before angular 17
new example
6. **Diferable views**
A fancy name given to the lazy-loading feature
old example before angular 17
new example
7. **More stable signals**
8. **Better build performance**
