
# The best all-in-one responsive and scalable code structure for Flutter

Responsive Design

If you are looking for an all-in-one scalable and responsive code structure for your Flutter application, you have come to the right place. This folder structure contains all the essential files required for your Flutter application, which manages the responsiveness, themes, routes, providers and more!

So let’s get started!

Suppose you are building an application compatible for the web, tablet and mobile platforms, you would ideally want to ensure that the user viewing your application has personalized views depending on the platform he/she wishes to use your application with.

Try viewing this website with your phone, or if on a web browser, resize the window, Link [HERE](https://dequeuniversity.com/library/responsive/1-non-responsive). You wouldn’t want your application to be like this. Would you? If you are looking to lose your users then go ahead! 😉

However, if you do want your cross platform Flutter application to scale well just like this website, Link [HERE](https://responsivedesign.is/examples/), carry on reading this article!

First things first though, I would like to give credits to [Filled Stacks](https://www.youtube.com/channel/UC2d0BYlqQCdF9lJfydl_02Q), an amazing YouTube channel teaching you how to build production ready Flutter applications. Feel free to check the channel out. His content has most certainly helped me grow as a Flutter Developer.

The code for the BaseWidget(SPOILER ALERT!) class as well as defining breakpoints, which you will find below, have been borrowed from his tutorial. I’ve further decided to elaborate on it and add my own twist to it, to make it easier for the readers to understand and duplicate on their projects easily.

## Responsive Design Pattern: A comprehensive definition.

Before getting into the folder structure, let’s formally define what a responsive design pattern is.

![Example Flutter Responsive UI](https://cdn-images-1.medium.com/max/3840/1*RmvcYMvi4YtXlJz-iXntTA.jpeg)*Example Flutter Responsive UI*

Simply put,
> “Responsive Web design is the approach that suggests that design and development should respond to the user’s behavior and environment based on screen size, platform and orientation.”

The ultimate goal is to allow the users who view your application, a comfortable experience no matter which device or platform they use.

## Responsive and Scalable Code Structure

Without any further delay, let’s get straight into the folder structure!

![Common Breakpoints for Different Platforms](https://cdn-images-1.medium.com/max/2400/1*ScNanqYCmVsKnRaPWosYIw.png)*Common Breakpoints for Different Platforms*

Given below is the basic layout of the folder structure.

![High Level Overview of the Folder Structure](https://cdn-images-1.medium.com/max/2000/1*HNJzIqE29Hczl9Vp4XH03A.jpeg)*High Level Overview of the Folder Structure*

This folder structure encapsulates all what’s needed for a scalable Flutter project.

Let’s start from the top, shall we?

### **Enumerations**

Enumerations are essential part of a programming language. They help developers defining small set of predefined sets of values that will be used across the logics they develop.

![Enumerations Folder](https://cdn-images-1.medium.com/max/2000/1*x6e_7Y2py2nSkejJL_60rw.jpeg)*Enumerations Folder*

<iframe src="https://medium.com/media/ef9cec575090f695e5e0531eec2fc921" frameborder=0></iframe>

This enumeration contains the three display types, i.e. Mobile, Tablet and Desktop.

### Models

Models represent knowledge. A model could be a single object or it could be some structure of objects. More often than not, a model can be used to parse a JSON file and the data can be fetched in an organized manner throughout the application using Providers or any similar state management technique.

![Models Folder](https://cdn-images-1.medium.com/max/2000/1*r-sN4PEasaa9iQjI7obtbA.jpeg)*Models Folder*

The first file above contains the Home View Model File:

<iframe src="https://medium.com/media/74c76f7d82f9845b39b9909a862d57c3" frameborder=0></iframe>

The above file initializes the Home View class which as we will see below is vital to display the appropriate class pertaining to the user platform.

The other file contains the Theme Model:

<iframe src="https://medium.com/media/dec849f557d0af3b4a512973c42d8185" frameborder=0></iframe>

Most modern apps contain two versions, light and dark modes. I prefer dark mode obviously!😊

This model makes it easier for the developer to toggle the themes using provider, as shown in the comment above.

### Providers

Provider State Management, which is recommended by the Google Flutter Team, mainly provides you a central point to manage the state of the application, and makes it really easy for the developers to share state and write front end logic closely connected to back end logic, thus enabling teams to work efficiently.

![](https://cdn-images-1.medium.com/max/2000/1*E2L-MrBN0TkNs9K6xNYaXQ.jpeg)

All the provider files would go under here, thus providing you a centralized location to manage all the state management processes in your Flutter Project.

### Responsive

As the folder name suggests, this folder contains all the necessary files which handles the breakpoints for different views, and the main responsive design pattern logic.

![](https://cdn-images-1.medium.com/max/2000/1*6K9IEh8BSoAlWB6g3dzfiA.jpeg)

The first class returns the current device orientation, it is especially useful if you want to separate the views into two, one for **Landscape **and the other **Portrait.**

<iframe src="https://medium.com/media/b4e15875643fb9693e5e71151731e957" frameborder=0></iframe>

As we can see, depending on the current device orientation, the Layout Builder returns the appropriate views for the same.

The next class which is the Responsive Builder handles the widget sizing properties relative to the current screen size using **Media Query**, thus painting the widgets appropriately. The Sizing Information is passed onto the next class which as we will see right below, splits the views depending on the user platform.

<iframe src="https://medium.com/media/a411abf815f6f27defda9364866e204b" frameborder=0></iframe>

A fact (which is pretty obvious at this point), is that it is also essential to build views depending on the current device platform, i.e., Mobile, Tablet and Desktop. This is exactly what the next class achieves.

<iframe src="https://medium.com/media/75a8e8e66532ac1c08034133dc6a9bff" frameborder=0></iframe>

Depending on the Sizing Information passed from the Responsive Builder class, the Screen Type Layout class returns the suitable platform.

Last, but definitely not the least, the next class is sort of a model; but is essential to the classes shown above. This class is responsible for the Sizing Information data, with respect to the user platform and is consumed by the above classes to extract the required screen sizing information.

<iframe src="https://medium.com/media/cddbecdc37b22894128052be43a52d1b" frameborder=0></iframe>

This sums up the all important responsive folder.

### Screens

This folder contains all your screens and their widgets respectively. They are separated based on orientation, furthermore, split on the basis of the platform i.e., Mobile, Tablet and Desktop.

![](https://cdn-images-1.medium.com/max/2000/1*mEnrNopvQ7tkl9A9wYRfFA.jpeg)

As we can see, the folder structure is pretty self explanatory. For now, I’ve loaded the folders with temporary Navigation Bar classes for each view, which for now, returns an empty container. Feel free to edit the class, or in fact start from scratch! It all depends on your design plans, so be creative!‎😃

This folder also contains the all important Home View class.

<iframe src="https://medium.com/media/6a14ac34ac7dd73aca27ac29b070355b" frameborder=0></iframe>

The Home View class provides the entry point to all other classes in your project, as we will see in the main file, this class redirects the route depending on the current orientation layout for that platform. Depending on your project requirements, you may change the route to your specific classes as per your design purposes.

### Services

The next folder is important, depending on if your app is connected to any backend database service such as Firebase. All the files required to fetch data from a database service goes here, and thus, separating both backend and frontend logic ideally.

![](https://cdn-images-1.medium.com/max/2000/1*bM-cLCe39ki3wcom6arB6w.jpeg)

### Utilities

The utilities folder holds all imports as we can see in the index file, the routes, constants and so on. This is absolutely vital to keep your source code clutter free and easy to read and understand. This helps the developer to easily manage all the utility services at one place, especially during the maintenance phase of the development cycle.

![](https://cdn-images-1.medium.com/max/2000/1*xq62-h8cfWoOV41BEVVp9w.jpeg)

The constants file, holds all the constant design components reused throughout the application. Two sample constant variables have been provided in the file to provide you a template on how constants are written and can be called globally on any screen requiring that particular component.

<iframe src="https://medium.com/media/9486c63326e1662416d2d43b10c9ef4d" frameborder=0></iframe>

Next up, in my humble opinion, is one of the most important files which helps in achieving clean clutter free code. It’s the index file. All your imports go here, thus avoiding duplication and a disarrangement of imports at the top of every file. Please do note that, not all imports may be exported globally.

<iframe src="https://medium.com/media/969a8711b0151c0db6da06428e4eff09" frameborder=0></iframe>

I’ve separated the imports even further depending on their type and the folder they belong too for your convenience. Hope this helps you out!

Next up is the routes file, and as the name suggests, holds all the routing logic for your application.

<iframe src="https://medium.com/media/bdca55d399328a34d67892943f724d22" frameborder=0></iframe>

For now the Routes class contains the route to Home View, which is the entry point to all other classes.

In order to get the current screen height and width, whether be it to responsively resize your image, or your container, this makes it easier to get the required information by just calling in the function and passing in the Build Context.

<iframe src="https://medium.com/media/d07152b5c6a59a012dfc460c708b9d94" frameborder=0></iframe>

Scaling the widgets with respect to the screen height and width is one of the most basic building blocks to responsive design.

For the theme model class mentioned above, we need a defined theme, through which you can style your Flutter projects. This is exactly what the below file contains.

<iframe src="https://medium.com/media/e38194efafd974f931928360f95f6902" frameborder=0></iframe>

For now, two sample themes for both dark and light modes have been given for your reference. Feel free to do the same, but this time using your own custom themes depending on your Flutter application!

The UI utilities file is pretty self explanatory. This file defines the breakpoints which your Flutter application adheres to while splitting up different views depending on the device or platform the user decides to view your application in.

<iframe src="https://medium.com/media/c5df6c9a4b480acc45327586c36ba32c" frameborder=0></iframe>

Currently, the breakpoints are based on the size of the shortest side, which seems to be a suitable measurement of the breaking point. As we can see, this function returns the device screen type, using the media query passed in as an argument.

### Widgets

The widgets folder, holds the common widgets between the screens mentioned above. This avoids duplication, as there would be reusable duplicate widgets between both the landscape and portrait orientation, and thus to avoid it, this approach is necessary.

![](https://cdn-images-1.medium.com/max/2000/1*Gxm3q4ubZYY0K-IVt9Hbvw.jpeg)

For now the common folder contains the common widgets of the Navigation Bar classes for each platform. For your Flutter project it maybe different, but nonetheless, the purpose of this folder remains the same.

The base widget class is needed to achieve the following:

![](https://cdn-images-1.medium.com/max/2000/1*iHD0Pf8_DQdXklBAxIKUmw.gif)

This class dynamically changes the design by altering the base class route depending on the screen orientation.

<iframe src="https://medium.com/media/614697f15b3c7cd73128a39ed7e3bc0b" frameborder=0></iframe>

As we can see, this class uses the Change Notifier Provider to dynamically respond the changes in screen dimensions globally throughout the Flutter Project.

### Main

Let’s start at the top of the widget tree, the main file!

This is the intro point to any Flutter application. In order to correspond to the above responsive design architecture, as well as including a very useful package which will help developers to view real-time design changes based on the platform, few changes have been made to the default main file.

<iframe src="https://medium.com/media/abcc4c7590cf47a06f0efc613cf9b439" frameborder=0></iframe>

The Device Preview package allows you to resize your Flutter application based on different pre-built devices such as an iPad Air, or a medium sized Android Tablet. It also has a free form tool which allows you to customize the size and thus build your application accordingly.

![Device Preview Package](https://cdn-images-1.medium.com/max/2000/1*A2cDM8G079FsYwUv3x8e4Q.gif)*Device Preview Package*

Furthermore, the initial route has been set to Home View, as we know it is the entry point which redirects the route to the respective class depending on the orientation. We also set the routes to correspond to the routes class.

This sums up our main file!

## Conclusion

As we have gone in-depth to all the folders and classes in the above code structure, we have reached the conclusion of this article.

This being my first medium article, I sincerely do hope that this walkthrough has proven to be useful for all the readers!

Please do ask you queries below in the comments section, and I will get back to you as soon as possible.

The source code, as well as the folder structure is free to download and integrate in your Flutter projects. Please do check it out below, and give it a star if it helps you out, much appreciated!
[**AlisterLuiz/Flutter-Responsive-Folder-Structure**
*Contribute to AlisterLuiz/Flutter-Responsive-Folder-Structure development by creating an account on GitHub.*github.com](https://github.com/AlisterLuiz/Flutter-Responsive-Folder-Structure.git)
