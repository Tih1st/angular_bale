# BaleMail made in Angular 
Followed guides to setting up Angular in VSCode and learning Angular it-self

(https://angular.io/guide/quickstart)

## Setting up Angular and first project
I followed the tutorial word for word with no errors until I got to Debugging with Chrome. The bug I had was that the debugging program was not registering my breakpoints with the message "Unverified breakpoint, Breakpoint ignored because generated code not found (source map problem?)" when attempting to debug for the first time. This is a common issue which I solved by going into my .vscode folder, and in my launch.json file, changed the line "webRoot": "${workspaceFolder}" to "webRoot": "${workspaceFolder}/my-app" and also added the line
"sourceMapPathOverrides": { "webpack:/*": "${webRoot}/*" }. This finally allowed me to use the debugger correctly.

## Tour of Heroes
Found [Here] (https://angular.io/guide/quickstart)

Again, I followed the steps word for word until I completed the tutorial. For additional practice, I incorporated the delete button into the hero-detail component, putting the same functions in and routing the user to the heroes tab with the deleted hero off the list. This helped me get used to Angular a little more.

After the tutorial, I wanted to learn about html and css more to better code in Angular, so I did a few tutorials over those languages.
Also did the tutorial here (https://coursetro.com/posts/code/154/Angular-6-Tutorial---Learn-Angular-6-in-this-Crash-Course)

## Static Website Hosting (Tour of Heroes)
Sucessfully hosted the Tour of Heroes site on Amazon s3

Result (http://testing-angular.s3-website.us-east-2.amazonaws.com/dashboard)

Create a new amazon s3 bucket, choose any valid bucket name, set Manage public permissions to Grant public permission. After this, go to properties tab, open Static Website Hosting and in the space for the index document, just enter index.html. We do not require an error document for this project. Afterwards, go to the permissions tab, into bucket policy, and add the below code in.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadForGetBucketObjects",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::bucket-name/*"
        }
    ]
}
```
Change bucket-name to your own bucket name.

Go back to your tour of heroes project and run **ng build**. This command will create a new dist file, in which you will upload to the bucket. At this point, the website should be up and running.

Now click the link found in the properties tab, in Static website hosting, and you will be be directed to your angular app!

