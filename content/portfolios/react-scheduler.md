---
title: "Interview-Scheduler: A React application"
date: 2021-12-05T14:04:51-05:00
draft: false
categories: 
    - React
weight: 2
ShowToc: true
TocOpen: true
cover:
    image: /images/portfolioImages/reactScheduler/1.jpg#center
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: ""
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---


React scheduler with up to five appointments per day. A dynamic and a true single-page application that utilizes various React hooks and states. This app utilizes asynchronous programming and testing tools like Jest for unit testing and integration testing and cypress.io for end-to-end testing.   

You can find this application running live on [React-Interview-Scheduler 🗓️](https://react-app-interview-scheduler.netlify.app/).  

Once you open the applicaiton, you may need to wait for three - four seconds or reload to fully load the app. I am using free tier for both services, so this is reasonable considering the price 😜.     

I have hosted this application on Netlify and Heroku using Postgres plugin. The server API on heroku provides the JSON data to the application, which is running on Netlify. 

## Final Product

### Opening page

Landing page, with up to five appointments per day and dynamic counter for the remaining spots.

![homepage](/images/portfolioImages/reactScheduler/opening.png#center)

### Creating a new appointment

Allows the creation (or edition) of an appointment, by entering the name and selecting the interviewer.

!["creating new appointment"](/images/portfolioImages/reactScheduler/creating.gif#center)

### Contextual warnings and Error handling

Warns the user if name field was left empty. As well as provides error when appointment cannot be set.

!["contextual error"](/images/portfolioImages/reactScheduler/error.gif#center)


### Transition states

Saving and deleting animated transitions.

!["state transitions"](/images/portfolioImages/reactScheduler/transition.gif#center)

### Storybook Component Tests

Built-in [storybook](https://storybook.js.org/) components tests.

!["storybook tests"](/images/portfolioImages/reactScheduler/storybook.png)

### Cypress E2E Tests

Built-in [cypress](https://www.cypress.io/) end to end tests.

!["cypress tests"](/images/portfolioImages/reactScheduler/cypress.png)

### Jest Unit Tests

Built-in [jest](https://jestjs.io/) test coverage.

!["jest tests"](/images/portfolioImages/reactScheduler/jestTest.png)

