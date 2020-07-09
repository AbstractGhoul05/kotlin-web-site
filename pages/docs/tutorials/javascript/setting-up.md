---
type: tutorial
layout: tutorial
title:  "Get started with Kotlin/JS for React"
description: "This tutorial demonstrates how to use IntelliJ IDEA for creating a frontend application with Kotlin/JS for React."
authors: Sebastian Aigner, Kate Volodko
date: 2020-07-07
showAuthorInfo: false
---

To get started, install a recent version of [IntelliJ IDEA](http://www.jetbrains.com/idea/download/index.html).

## Create an application 

Once you've installed IntelliJ IDEA, it's time to create your first frontend application based on Kotlin/JS with React.

1. In IntelliJ IDEA, select **File** \| **New** \| **Project**.
2. In the panel on the left, select **Kotlin**.
3. Enter a project name, select **Frontend Application** as the project template, and click **Next**.
   
   ![Kotlin frontend application]({{ url_for('tutorial_img', filename='javascript/setting-up/js-new-project-1.png') }})
   
   By default, your project will use the build system Gradle with Kotlin DSL.

3. Accept the default configuration on the next screen and click **Finish**.
  
   ![Frontend application configuration]({{ url_for('tutorial_img', filename='javascript/setting-up/js-new-project-2.png') }}) 

   Your project opens. By default, you see the file `build.gradle.kts`, which is the build script created by the Project 
   Wizard based on your configuration. It includes the `kotlin("js")` plugin and dependencies required for your frontend application.


## Run the application

Run the application by clicking **Run** next to the run configuration at the top of the screen.

<img class="img-responsive" src="{{ url_for('tutorial_img', filename='javascript/setting-up/js-run-app.png') }}" alt="Running a frontend app" width="500"/>

Your default web browser opens the URL `localhost:8080` with your frontend application.

<img class="img-responsive" src="{{ url_for('tutorial_img', filename='javascript/setting-up/js-output-1.png') }}" alt="Web browser with JS application"/>

Enter your name in the text box and accept greetings from your application!

## Update the application

### Show your name backwards

1. Open the file `welcome.kt` in **src** \| **main** \| **kotlin**.  
   The **src** directory contains Kotlin source files and resources. The file `welcome.kt` includes sample code that renders 
   a web page you've just seen.

   ![Source code for frontend application]({{ url_for('tutorial_img', filename='javascript/setting-up/js-welcome-kt.png') }})

2. Change the code of `StyledDiv` to show your name backwards.  
   
   * Use the standard library function `reversed()` to reverse your name.
   * Use your reversed name right in text output by adding `$` and enclosing in curly brackets `{}` - `${state.name.reversed()}`.
   
   <div class="sample" markdown="1" theme="idea" mode="kotlin" data-highlight-only>
   
   ```kotlin
   styledDiv {
               css {
                   +WelcomeStyles.textContainer
               }
               +"Hello ${state.name}!"
               +" Your name backwards is ${state.name.reversed()}!"
           }
   ```
   
   </div>
   
3. Save changes to the file.

4. Go to the browser and enjoy the result.
   
<img class="img-responsive" src="{{ url_for('tutorial_img', filename='javascript/setting-up/js-output-2.png') }}" alt="Web browser with a reversed name" />

### Add an image

1. Open the file `welcome.kt` in **src** \| **main** \| **kotlin**.  

2. Add the `div` element with an image `img`.  
   
   > Make sure that you import these packages - `react.dom.*` and `styled.*`.
   {:.note}       
   
   <div class="sample" markdown="1" theme="idea" mode="kotlin" data-highlight-only>
   
   ```kotlin
   div {
           img(src = "https://placekitten.com/408/287") {}
       }
   ```
   
   </div>                                                                                                                                                                                                                                                        >
   
3. Save changes to the file.

4. Go to the browser and enjoy the result.
   
<img class="img-responsive" src="{{ url_for('tutorial_img', filename='javascript/setting-up/js-output-3.png') }}" alt="Web page with with an image" width="500"/>

### Add a button that changes text

1. Open the file `welcome.kt` in **src** \| **main** \| **kotlin**.  

2. Add the `button` element with the `onClickFunction` event.  
   
   > Make sure that you import the package `kotlinx.html.js.*`.
   {:.note}         
   
   <div class="sample" markdown="1" theme="idea" mode="kotlin" data-highlight-only>
   
   ```kotlin
    button {
        attrs.onClickFunction = {
            setState(
                    WelcomeState(name = "Some name")
            )
        }
        +"Change name"
    }   
   ```
   
   </div>                                                                                                                                                                                                                                                              >
   
3. Save changes to the file.

4. Go to the browser and enjoy the result.
   
<img class="img-responsive" src="{{ url_for('tutorial_img', filename='javascript/setting-up/js-output-4.png') }}" alt="Web page with a button" width="500"/>


