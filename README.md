# Official JSX Shared Resources Class Library of the jSilvestri.com BETA v 2024 Web API Demo Collection

The `JsxSharedResources` application (i.e., _jSilvestri.com BETA v 2024 JSX Shared Resources Class Library_) in specific, is a FREE, open-source, custom, reusable, jSilvestri.com 2024 Web API Demo Collections ASP.NET Core 8 Class Library, and a project that contains shared static resources (HTML files, images, JavaScript, and CSS) used across multiple client projects, including `JsxAngularWebApiDemo`, `JsxReactWebApiDemo`, `JsxVueWebApiDemo`, and `JsxBlazorWebApiDemo`. This project ensures consistency and simplifies the management of these resources.

## Overview

The `jSilvestri.com BETA v 2024` mobile and web applications, developed for most smart phones, tablets and desktop computers, was created to showcase a wide range of skills to potential clients and employers, while providing helpful information to fellow developers, demos for interview talks, access to resumes, etc.

The `JsxSharedResources` application (i.e., _jSilvestri.com BETA v 2024 JSX Shared Resources Class Library_) in specific, is a FREE, open-source, custom, reusable, jSilvestri.com 2024 Web API Demo Collections ASP.NET Core 8 Class Library, and a project that contains shared static resources (HTML files, images, JavaScript, and CSS) used across multiple client projects, including `JsxAngularWebApiDemo`, `JsxReactWebApiDemo`, `JsxVueWebApiDemo`, and `JsxBlazorWebApiDemo`. This project ensures consistency and simplifies the management of these resources.
Many applications in the `Custom jSilvestri.com BETA v 2024 Web API Demo Collection`, such as the `Angular Web API Demo`, `Blazor Web API Demo`, `React Web API Demo`, and `Vue Web API Demo` applications will use this project to reference common features throughout the collective applications.

### Key Components

- **HTML**: Contains shared HTML files.
- **images**: Contains shared image files.
- **javscript**: Contains shared JavaScript files.
- **lib**: Contains shared assets related to JavaScript files.
- **css**: Contains shared CSS files.

## Getting Started

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Visual Studio 2022 or higher](https://visualstudio.microsoft.com/)
- [Visit jSilvestri.com BETA v 2024 Demos for More Details](https://jsilvestri.com/home/demo)
  

### Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/JasonSilvestri/jSilvestri2024WebApiDemoCollection.git
    ```

2. **Open the solution in Visual Studio**:

    - Open `jSilvestri2024WebApiDemoCollection.sln` in Visual Studio.

3. **Restore NuGet packages**:

    - Right-click on the solution in Solution Explorer and select `Restore NuGet Packages`.

4. **Build the solution**:

    - Right-click on the solution in Solution Explorer and select `Build Solution`.

## Adding Static Files

1. **Add your static files** to the respective folders in the `JsxSharedResources` project (`HTML`, `images`, `JavaScript`, `CSS`).

2. **Set the Build Action** for these files to `Content` or `Embedded Resource`:
    - Right-click on the files in each folder in Solution Explorer.
    - Select **Properties**.
    - Set the **Build Action** to `Content` or `Embedded Resource`.

## Using Shared Resources in Client Projects

### Reference the Shared Resources Project

1. **Add a project reference** to `JsxSharedResources` in each client project:
    - Right-click on the client project (e.g., `JsxAngularWebApiDemo`, `JsxReactWebApiDemo`, `JsxVueWebApiDemo`, `JsxBlazorWebApiDemo`).
    - Select **Add** > **Project Reference**.
    - Check `JsxSharedResources` and click **OK**.

### Example: Blazor Project

**In `JsxBlazorWebApiDemo`**:

1. **Reference the Shared Resources Project**:
    - Add a reference to `JsxSharedResources` in `JsxBlazorWebApiDemo`.

2. **Use Static Files in Razor Components**:
    - Create a Razor component that uses the shared static files.

    ```razor
    @page "/example"
    @inject IWebHostEnvironment env

    <h3>Example Page</h3>

    <img src="@($"{env.WebRootPath}/images/logo.png")" alt="Logo">
    <script src="@($"{env.WebRootPath}/JavaScript/script.js")"></script>
    <link rel="stylesheet" href="@($"{env.WebRootPath}/CSS/style.css")">
    ```

### Example: Angular Project

**In `JsxAngularWebApiDemo`**:

1. **Copy Files Using a Build Script**:
    - Create a script to copy the shared resources from `JsxSharedResources` to the `assets` folder of the Angular project during the build process.

    ```json
    // package.json
    "scripts": {
        "postinstall": "npm run copy-shared-resources",
        "copy-shared-resources": "cp -r ../JsxSharedResources/* ./src/assets/"
    }
    ```

2. **Use Static Files in Angular Components**:
    - Reference the static files in your Angular components.

    ```html
    <!-- app.component.html -->
    <img src="assets/images/logo.png" alt="Logo">
    <script src="assets/JavaScript/script.js"></script>
    <link rel="stylesheet" href="assets/CSS/style.css">
    ```

### Example: Vue Project

**In `JsxVueWebApiDemo`**:

1. **Copy Files Using a Build Script**:
    - Create a script to copy the shared resources from `JsxSharedResources` to the `assets` folder of the Vue project during the build process.

    ```json
    // package.json
    "scripts": {
        "postinstall": "npm run copy-shared-resources",
        "copy-shared-resources": "cp -r ../JsxSharedResources/* ./public/assets/"
    }
    ```

2. **Use Static Files in Vue Components**:
    - Reference the static files in your Vue components.

    ```html
    <!-- App.vue -->
    <template>
        <div>
            <img src="assets/images/logo.png" alt="Logo">
            <script src="assets/JavaScript/script.js"></script>
            <link rel="stylesheet" href="assets/CSS/style.css">
        </div>
    </template>
    ```

### Example: React Project

**In `JsxReactWebApiDemo`**:

1. **Copy Files Using a Build Script**:
    - Create a script to copy the shared resources from `JsxSharedResources` to the `public` folder of the React project during the build process.

    ```json
    // package.json
    "scripts": {
        "postinstall": "npm run copy-shared-resources",
        "copy-shared-resources": "cp -r ../JsxSharedResources/* ./public/assets/"
    }
    ```

2. **Use Static Files in React Components**:
    - Reference the static files in your React components.

    ```javascript
    // App.js
    import React from 'react';

    function App() {
        return (
            <div>
                <img src="assets/images/logo.png" alt="Logo" />
                <script src="assets/JavaScript/script.js"></script>
                <link rel="stylesheet" href="assets/CSS/style.css" />
            </div>
        );
    }

    export default App;
    ```

## Conclusion

This guide provides an overview of setting up the `JsxSharedResources` project to manage shared static resources and using these resources in various client projects (`JsxAngularWebApiDemo`, `JsxReactWebApiDemo`, `JsxVueWebApiDemo`, and `JsxBlazorWebApiDemo`). Follow the instructions to ensure your projects can consistently and efficiently utilize shared resources.

## Planned Evolution of jSilvestri.com BETA v2024 Web API Demo Collection

Depending on when you visit this demo application, it may look very different from your previous visit. I am not talking about common checkins to improve the applications. I am talking about noticable, planned, development that will shape each application in accordance to the grand design. In other words, the variability is intentional. 

The purpose of this project, and its associated projects, is to showcase my basic skills in the technologies I am currently exploring in 2024. By leveraging my 20 years of experience in full stack development and solution architecting, I aim to address areas often overlooked in typical online examples, such as security, object-oriented coding, and the transformation of existing assets, templates, and projects into custom creative designs that support specific objectives.

The target technologies and project structures include **AngularJS**, **Vue**, **ReactJS**, and **Blazor**, all of which access the same Web API project using ASP.NET Core 8 and Visual Studio 2022 (or higher).

### Source Control Strategies

There are typically two primary ways to handle source control for multiple projects:

1. **Monorepo**: Storing all projects within a single GitHub repository. This approach simplifies managing dependencies and integrations between projects and ensures consistency across the solution.
2. **Multi-repo**: Creating separate GitHub repositories for each project. This approach provides greater modularity and allows each project to evolve independently, which can be beneficial if projects have different development cycles or teams.

We will use a combination of both approaches. This hybrid method allows potential clients, employers, and fellow developers to download and run the applications they are most interested in as standalone projects (i.e., _AngularJS_, _Vue_, _ReactJS_, or _Blazor_), all accessing the same Web API project using ASP.NET Core 8 and Visual Studio 2022 (_or higher_), each with their own project and solution. Additionally, this approach ensures we can also create a project and solution that includes all applications, facilitating easy transitions between tiers for various needs (i.e., the _jSilvestri.com BETA v 2024 Web API Demo Collection Project_).

### Project Development Steps - Phase 1:

While this workflow may change, the steps I am taking to conclude all aspects of the project development are as follows:

1. **Add a Class Library**: Add a new ASP.NET Core Class Library project and solution. This project will serve as the common place where we share the most common class and interface parts we want to use across all applications, such as Constants, Enums, Helpers, etc.
   
2. **Add a Web API Project**: Add a new ASP.NET Core Web API project and solution. This project will serve as the backend API that the frontend projects will communicate with.

3. **Add a Shared Assets Project**: Add a new ASP.NET Core project and solution that will handle common, static, assets and resources, shared across all applications. This project will serve as the resource project with all HTML, CSS, JS, Images and other creative all projects will use to carry the same theme, look and feel across applications. For now, all projects will use the basic, out-of-the-box vanilla assets.

4. **Add Frontend Projects**:
   - Add separate projects and solutions for AngularJS, Vue, ReactJS, and Blazor. We will initially choose the appropriate project templates provided by Visual Studio.
   - For AngularJS, Vue, and ReactJS, we will consider creating separate ASP.NET Core Web Application projects and choosing the respective frontend frameworks (i.e., _Angular_, _Vue.js_, _React.js_) during project creation.
   - For Blazor, we will create a Blazor WebAssembly or Blazor Server project, depending on your preference. If I have bandwidth, I may also create a Blazor Hybrid Project, which is relatively new to the scene.

5. **Setup Communication**:
   - Each frontend project (_AngularJS_, _Vue_, _ReactJS_, _Blazor_, etc.) will make HTTP requests to the Web API project to fetch data or perform operations. For the first iteration of data, we will use some static weather data. 

6. **Configure Routes**:
   - We will define appropriate routes in our Web API project to handle incoming requests from the frontend projects.
   - We will implement controllers and actions to handle these routes and interact with our data layer.

7. **Web API Shared Models and Services**:
   - We will consider creating shared models and services that can be used across both the Web API project and the frontend projects. This will help in maintaining consistency and reducing duplication of code.

8. **Authentication and Authorization (Optional)**:
   - Implement authentication and authorization mechanisms in Web API project if required (final version should).

9. **Testing and Debugging**:
   - Test the communication between the frontend projects and the Web API project.
   - Debug any issues that arise during development.

10. **Deployment**:
    - Deploy the Web API project and frontend projects to the desired hosting environment. Ensure that all projects are configured correctly for production.

11. **Continuous Integration and Continuous Deployment (CI/CD)**:
    - Set up CI/CD pipelines to automate the build and deployment process for your solution.


### Project Development Steps - Phase 2:

While this workflow may change, the steps I am taking to conclude all aspects of the project development are as follows:

1. **Update Class Library**: Update ASP.NET Core Class Library project and solution parts we want to use across all applications, such as Constants, Enums, Helpers, etc.
   
2. **Update Web API Project**: Update ASP.NET Core Web API project and solution. This project will serve as the backend API that the frontend projects will communicate with.

3. **Update Shared Assets Project**: Update new ASP.NET Core project and solution that will handle common, static, assets and resources, shared across all applications. This project will serve as the resource project with all HTML, CSS, JS, Images and other creative all projects will use to carry the same theme, look and feel across applications.

4. **Add All Frontend Projects, Assets Projects & Web API to jSilvestri.com BETA v2024 Web API Demo Collection Solutions**:
   - Clone all projects and add them to the jSilvestri.com BETA v2024 Web API Demo Collection project for full access and testing of all projects in one, unified, location.

5. **Setup Communication**:
   - Each frontend project (_AngularJS_, _Vue_, _ReactJS_, _Blazor_, etc.) will make HTTP requests to the Web API project to fetch data or perform operations. The final version will access real-time weather data from one or more weather APIs available today.
   - Ensure that CORS (_Cross-Origin Resource Sharing_) is properly configured in the Web API project to allow requests from the frontend projects.

6. **Configure Routes**:
   - We will define appropriate routes in our Web API project to handle incoming requests from the frontend projects.
   - We will implement controllers and actions to handle these routes and interact with our data layer.

7. **Shared Models and Services**:
   - We will consider creating shared models and services in their own project, as opposed to housing them in the Web API project that can be used across both the Web API project and the frontend projects. This will help in maintaining consistency and reducing duplication of code.
   - An eventual version of this approach will leverage a structure where we have specific repositories for each service along with a generic repository to handle common CRUD operations, following a design pattern like the Repository Pattern.

8. **Authentication and Authorization (Optional)**:
   - We will use JWT (_JSON Web Tokens_) for authentication and role-based authorization.

9. **Testing and Debugging**:
   - Test the communication between the frontend projects and the Web API project.
   - Debug any issues that arise during development.

10. **Deployment**:
    - Deploy the Web API project and frontend projects to the desired hosting environment. Ensure that all projects are configured correctly for production.

11. **Continuous Integration and Continuous Deployment (CI/CD)**:
    - Set up CI/CD pipelines to automate the build and deployment process for your solution.

**Copyright © 2024 - All Rights Reserved by Jason Silvestri**