## NPM or NPX ???

Hello World !!

If you are working with JavaScript, you probably heard about  [NPM](https://www.npmjs.com/package/npm)  and  [NPX](https://www.npmjs.com/package/npx) . You have used this to install something on your JavaScript project.

In this blog, we are going to see difference between NPM and NPX. Let's understand both of them.

**NPM** (**Node Package Manager**) is a dependency/package manager we get, while we install Node. With the help of NPM we can maintain/manage dependency on both global and local level. Later, NPX tool is bundled with NPM, which is also used for package management. Both NPM and NPX is a dependency/package management tool but they both treat packages differently.


## What Is NPM ?

NPM stands for **N**ode **P**ackage **M**anager. It comes preinstalled with Node JS. It is written entirely in JavaScript. 

NPM manages all the packages and modules for Node js, with the help of NPM command-line client. Any required packages is going to be installed in our application using NPM.  

## What Is NPX ?

NPX is a **N**PM **P**ackage **e**xecutor. NPX is also just an NPM package that could be installed like other NPM packages. Now, NPX is bundled with NPM when you install NPM version 5.2.0 or higher.

## How NPM treat Node Packages ?

NPM sets up packages/modules in such way that Node js can locate the package and manage the dependencies as per the requirement of project.

If we are using NPM, we have two ways to install packages into our local system.

- **Locally**: When a package is installed locally, it is installed in `./node_modules/.bin/` of the local project directory. 

- **Globally**: When a package is installed globally, it is installed in user environment path. `/usr/local/bin` for Linux and `AppData%/npm` for Windows.

When we install package using NPM, Node js links that particular package either from local or from global path. NPM does not execute the package directly.

To use and run an NPM installed package, we need to specify the package in the `package.json` file. The `package.json` file is created automatically when we initialize our Node js project with `npm init -y`.

If we want to execute locally installed package then that package should be mentioned in `package.json` script block as shown below.

![carbon (13).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640712609640/OLh8PQpMR.png)

Now, we can use `npm run` command to run random package scripts.

![carbon (14).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640712857775/xFd5SHHY7.png)

On the other side, we can type the package path in a command-line tool also.

![carbon (15).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640712993895/mA1JOiesM.png)


Now, as we can see that just running a package just with plain NPM is quite a bit of long process. This is where NPX comes in use to help us.

## Using NPX

With NPX, we can run and execute packages without installing them locally or globally. After NPM version 5.2.0, NPX is pre-bundled with NPM.

When running NPM packages with NPX, if a package is installed, NPX will search for the package binaries on local or global path and then run the package.

But, if the package is not installed in system, then NPX will not install the package in system. Instead of installing the package, NPX will create temporary cache that will hold particular package binaries. Once, the execution is over NPX will remove this temporary created cache which is holding package binaries for execution.

Using NPX our globals related to packages stays clean. Also, we can save our disk space and run the package only when it's needed. Also, it gives us the advantage of testing different kinds of package without installing them in our system.

Let's see some use cases of NPX.

First, run following command to verify to check you have NPX installed in your system. `npx -v`

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640714277214/_9b4lbPDz.png)

To execute a package with NPX, we need to use below command.

![carbon (16).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640714459143/P-XmhsEDb.png)

Let's see one example where package is not installed as locally or globally in our system.

![Capture.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1640714793237/3jo8j9n1m.png)

## Why NPX over NPM scripts?

- No need to edit the `package.json` file with `node_modules` paths.

- You can directly execute the tool from the command line.

## Test different package versions using NPX

With the help of NPX, we can easily test different versions of a package or modules very easily.

Here, we are going to test this as installing the create-react-app package and test out an upcoming version in local.

We need to run `npm v create-react-app` command. After running this command, we can see some `dist-tags` at the end of output. Using this dist-tags we can specify particular version number to create app.

![Capture (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640715825327/EoDheF0JRz.png)

Let’s use NPX to try out the next dist tag of create-react-app which will create the react app in defined ReactApp folder,

Run below command for the same:

![carbon (18).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640716228979/5H80QnFxv.png)
 
Using this method we can test different package versions using NPX.


## Conclusion

NPX helps us to avoid version and dependency management related issues. Also with NPX we can directly run particular package without installing them for our testing. Using this method, our global path related to NPM stays clear and also we can save disk space using this.


Thank you for reading, I hope you found this article useful.

If you enjoyed reading, please consider following me here on Hashnode and also on  [Twitter](https://twitter.com/Its_SR__)  /  [GitHub](https://github.com/sahilrajput2223)  /  [LinkedIn ](https://www.linkedin.com/in/rajputsahil/) . 






