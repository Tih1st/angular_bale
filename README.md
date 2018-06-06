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
Result (http://testing-angular.s3-website.us-east-2.amazonaws.com/dashboard)
Run ng build in terminal, upload all files in new dist folder to bucket,add this to permissions

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

Change bucket-name to your own bucket name.

Set-up static website hosting in Properties, enter ndex.html for the index and leave error blank. 
Now click the link to be directed to your angular app!

