# Sentry Basics
Sentry is a real-time error tracking system that gives you insight into production deployments and information to reproduce and fix crashes. 

Sentry has some prominent features:

- It allows you to get notifications via email, sms or just use their website console.
- It lets you know what’s breaking and how to reproduce the problem, without waiting for user reports. 
- It lets you view actual code in stack traces and see the error’s url, parameters, and session information.

A powerful tool like Sentry requires some time to learn and master. In this tutorial we will go through the basic usage of it and by the end of this scanario, you should know how to setup everything and explore the fundamental usage of Sentry.

Before you start, here are some key terms that might help you during the process:

- **sentry.io** - Sentry's user interface for SaaS customers, where event data captured by our SDK is visualized. (For self-hosted users, the user interface is on an internal domain for your company.)
- **project** - A project represents your service or application in Sentry. You can create a project for a particular language or framework used in your application.
- **DSN** - Data Source Name. A DSN tells the Sentry SDK where to send events so the events are associated with the correct project. 

If you want to know more about these, you can refer to their [doc](https://docs.sentry.io/product/sentry-basics/key-terms/)