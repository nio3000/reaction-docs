# Frequently Asked Questions
## General
### What do I need to know to work with Reaction?

To start customizing Reaction, you should probably have a basic understanding of the following technologies:
- JavaScript, specifically ES6
- HTML/CSS
- Some knowledge of Meteor, especially an understanding of [Publications and Subscriptions](https://guide.meteor.com/data-loading.html)
- A front-end framework/library like React

Reaction tries to be as modular as possible. All user customizations are intended to live in plugins, as they provide a secure upgrade path when new versions are rolled out. See [here](/developer/tutorial/plugin-intro-1.md) for a more detailed explanation into the plugin topic.

### What sites are built on Reaction Commerce?

Ecommerce and marketplace sites from around the world are using Reaction in production now. Check out our [Community Showcase](https://reactioncommerce.com/community-showcase).

#### Why is Reaction so slow?

*For Development*

We are aware that Reaction Commerce can take a long time to reload when using the development server. This has to do with that
large amount of files that are in the project. Hopefully this has been mitigated to some degree with the update to Meteor 1.6, however
we know that faster is better when it comes to development so we will be focusing all of our efforts on improving performance. You
can see our plan, weigh in with suggestions, contribute, and track progress [here](https://github.com/reactioncommerce/reaction/issues/3233)

*To "first paint"*

As mentioned above we are aware that because of the nature of Meteor apps and the size of this app that on some connections
it can take several seconds before the site is rendered to clients. We are working to reduce the bundle size by eliminating some
package and moving to a more dynamic loading so that parts of the app that may not be needed till later are not sent to the client on first
load. Performance will be our main focus until the problem is resolved.
You can see our plan, weigh in with suggestions, contribute, and track progress [here](https://github.com/reactioncommerce/reaction/issues/3233)

### Can I compile a mobile app from Reaction? Are you going to develop a mobile app?

While Meteor allows all apps to be compiled into Android and iOS apps with Cordova, we do not support it. Setting up a Reaction app with Cordova may be difficult. Learn more about building [mobile apps with Meteor's Cordova integration](https://guide.meteor.com/mobile.html).

While we do have plans to work on a mobile app on the [Roadmap](https://reactioncommerce.com/roadmap), we expect to use a non-Cordova approach, like React Native. We do not have a release date.

What's important to know, however, is that Reaction Commerce takes a "mobile first" design approach to ensure that both the consumer-facing and admin-facing sites are functional on most modern mobile devices.
 
## Installation

### I cloned the Reaction repo but when I run `meteor` it doesn't work

You need to install and use the Reaction command line tool in order to run Reaction. It does some work building the application
before the app starts that is not optional. You can install the CLI by doing `npm install -g reaction-cli`. Then you should be able to run `meteor npm install` and then start the app by running `reaction run` or just `reaction`.

### Do you have a list of community provided plugins, themes or other resources?

We compiled a curated list of community projects that can be found in the wild. Over time this list will continue to grow and some of the project's may become deprecated. Please drop us a note if you spot new awesome contributions out there!
[Community Resources](/developer/community-resources.md).


## Deployment

### What is the best place to host?

Here are some options for deployment. What the best options is depends on your budget and your expected level of traffic

1. Reaction Platform

The Reaction Platform comes with virtual private clusters, containerized cloud hosting, multiple staging environments, SSL and domains, direct support channels, and one-step deployment.

Reaction Commerce’s Platform enables clients to : 
1. innovate faster by leveraging modern container-based technology that provides continuous integration, delivery, and deployment.  
2. more effectively and efficiently manage your site with seamless cutovers, dynamic scaling, and multiple “everything”
3. have greater peace of mind from our high availability, virtual clusters, and 24x7x365 support.

You can find out more and request a quote [here](https://reactioncommerce.com/#get-a-demo) or you can contact sales@reactioncommerce.com.

2. Galaxy

The Meteor Development Group offers a hosting service that is focused on hosting Meteor apps with monitoring, etc. You can find
more information [here](https://www.meteor.com/hosting)

### What about services like Heroku, or running on EC2?

You can deploy Reaction Commerce to anywhere you could deploy a Docker container or a Node app. Because of the complexities involved
we currently can't offer any support for getting these deployed.

## Admin

### Where is the admin panel?

The login panel is visible on the right side, once you login as a user with admin credentials. For more on navigating admin, read our [Reaction Commerce Store Operator Guide](/admin/dashboard.md).

### What's the admin login?

By default the admin login will be username: `admin@localhost` and password `r3@cti0n`

### What about SEO?

Since 2014 [Google has indexed JavaScript when crawling websites](https://webmasters.googleblog.com/2014/05/understanding-web-pages-better.html). Reaction, however, offers page pre-rendering and product detail page metatag generation out of the box to ensure products are indexed well for web crawlers and search engines:

1. [Prerender.io](https://prerender.io/): Reaction includes integration with Prerender.io out of the box. Prerender.io is a commercial service that will generate static renderings of the application for search engines. ALl you have to do is provide a key to your site and Prerender will handle the pre-rendering.

2. [Spiderable](https://github.com/ongoworks/spiderable): A now-deprecated solution is our Atmosphere package called (Spiderable)[https://atmospherejs.com/ongoworks/spiderable] that pre-renders Meteor applications for search engines.

3. [meteor-dochead](https://github.com/kadirahq/meteor-dochead): Automatically add `<meta>` tags are for products using the [meteor-dochead](https://github.com/kadirahq/meteor-dochead) package which uses the title, description and `details` fields of the product to render SEO-friendly data. You may need to use a tool like [SEO Inspector](https://chrome.google.com/webstore/detail/seo-inspector/iejckekdjogeeilmllnabmgkbbmedeal?hl=en) to see this data.

## Extending Reaction

### How can I add add a static page?

Add a single page, and more child pages, by adding a route and a template. This will require knowledge of HTML, JavaScript and Git or web development. This is covered in depth in this section of the [Customization Guide](https://docs.reactioncommerce.com/reaction-docs/master/plugin-routes-6).

This would work great for static pages like an About or Contact us page. If you want to add tools for administrators to manage text and image content without having to code, you probably want to a content management system (CMS).

### How do I integrate with a content management system (CMS)?

If you have a lot of content (like images and text) that needs to be managed you probably want to use a content management system (CMS). We currently do not have one integrated with Reaction.

On our [roadmap](https://reactioncommerce.com/roadmap)
we have a planned integration with a CMS like Drupal, which can hopefully serve as a model for other similar integrations.

## More

### I have another question. Where's the best place to ask it?

You can post questions in Gitter chat about [Installation](https://gitter.im/reactioncommerce/installation), [Deployment](https://gitter.im/reactioncommerce/deployment), [general Reaction](https://gitter.im/reactioncommerce/deployment) topics and [Architecture](https://gitter.im/reactioncommerce/architecture). You can also post questions in the [Forums](https://forums.reactioncommerce.com/).

Want more help? You can also ask a question live during our Community Calls. Here's the past [agendas](https://docs.google.com/document/d/1PwenrammgQJpQfFoUUJZ96i_JJYCM_4glAjB1_ZzgwA/edit) and a form to [submit questions] (https://docs.google.com/forms/d/e/1FAIpQLSfsNNH1W4bP7k4Gkl1JYF4vCEwQcHE9X3OIFfTH2TNwD7dN4Q/viewform).
