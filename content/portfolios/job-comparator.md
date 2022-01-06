---
title: "Job-Comparator: An Android Application"
date: 2021-09-20T14:04:51-05:00
draft: false
categories: 
    - Android
weight: 2
cover:
    image: /images/portfolioImages/jobcomparator/1.jpg#center
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "pizza-image"
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---


# Job Comparison App User Manual

## Introduction

Job Comparison App is an Android mobile app which allows a user to compare job offers using customizable settings.

## System requirements

Job Comparison App requires Android version 10 (Android Q) and Pixel 4 XL.

## Features and functionalities

### Main menu

When the app starts, a main menu is displayed and it allows the user to choose one of the four options:

- Enter or edit current job details
- Enter job offers
- Adjust the comparison settings
- Compare job offers (enabled if there are 2 or more jobs).

<img src="/images/portfolioImages/jobcomparator/main_menu.png#center" width="300">

### Enter or update current job

When a user clicks the `CURRENT JOB` button in main menu, user can enter details of the user's current job, and save it for future job comparison. If user has previously saved the Current Job then the data is pre-filled, if not then the input fields would be blank. 
The following job details can be entered:

- Title
- Company
- Location (entered as city and state)
- Cost of living in the location (expressed as an index)
- Yearly salary
- Yearly bonus
- Allowed weekly telework days (expressed as the number of days per week allowed for remote work, inclusively between 0 to 5 days)
- Leave time (vacation days and holiday and/or sick leave, as a single overall number of days per year, inclusively between 0 to 260 days)
- Gym membership allowance (inclusively $0 to $500 annually)

If user chooses to cancel, the current job will not be saved. If user chooses to save, the current job will be saved and can be updated in the future. Once user cancel or save, the app will return to the main menu.

<img src="/images/portfolioImages/jobcomparator/current_job_1.png#center" width="300">

<img src="/images/portfolioImages/jobcomparator/current_job_2.png#center" width="300">

<img src="/images/portfolioImages/jobcomparator/current_job_3.png#center" width="300">

### Enter job offers
When a user clicks the `ENTER JOB OFFERS` button in the main menu.  The user will be shown a user interface to enter all of the details of the job offer, which are the same ones listed above for the current job. 

The following job details can be entered:
- Title
- Company
- Location (entered as city and state)
- Cost of living in the location (expressed as an index)
- Yearly salary
- Yearly bonus
- Allowed weekly telework days (expressed as the number of days per week allowed for remote work, inclusively between 0 to 5 days)
- Leave time (vacation days and holiday and/or sick leave, as a single overall number of days per year, inclusively between 0 to 260 days)
- Gym membership allowance (inclusively $0 to $500 annually)

<img src="/images/portfolioImages/jobcomparator/job_offer.png#center" width="300">


After entered all the details, the user is able to either save the job offer details or cancel.

<img src="/images/portfolioImages/jobcomparator/job_offer_save_cancel.png#center" width="300">


After save successfully, the user is able to enter another job offer, compare it with current job if current job exist, or return to the main menu.

<img src="/images/portfolioImages/jobcomparator/job_offer_after_save.png#center" width="300">


### Adjust Comparison Settings

When a user Click on the `COMPARISON SETTINGS` on the main menu, a form will open with comparison settings values pre-filled. These values are persistent locally in the device. Initially all the settings has default values of 1. This indicates, that all parameters will be weighted equally when computing a score for the Job offers.  

<img src="/images/portfolioImages/jobcomparator/comparisonSettings_screenShot.png#center" width="300">

- User can edit these values and assign any integer value including 0 to 100. A numeric Keypad will open to edit the values. These settings fields can not be empty. Two buttons at the bottom of the form allow user to either save the updated settings or return to the main menu without making any changes. Once a user click `SAVE` button, it will update the settings and redirect to the main menu. A success notification will show on the screen upon successful update.   

<img src="/images/portfolioImages/jobcomparator/editComarisonSettings_screenShot.png#center" width="300">

<img src="/images/portfolioImages/jobcomparator/updateComparisonSettings_screenShot.png#center" width="300">

### Compare Jobs

User will be shown a list of job offers, including the current job, ranked from best to worst based on the weights set in the comparison settings. Current Job will be clearly labeled above the Job title. User can select two jobs to compare and trigger a comparison using the `COMPARE JOBS` button. `COMPARE JOBS` button would be disabled unless two jobs are selected. User can click on the `CANCEL` button to go back to the main menu. 

<img src="/images/portfolioImages/jobcomparator/compare_jobs_1.png#center" width="300">

<img src="/images/portfolioImages/jobcomparator/compare_jobs_2.png#center" width="300">

Once a user selects two jobs and clicks `COMPARE JOBS` button, it will show the comparison in the form of a table displaying the following information about each selected job:  

- Title
- Company
- Location (city and state)
- Yearly salary adjusted for cost of living
- Yearly bonus adjusted for cost of living
- Allowed weekly telework days
- Leave time
- Gym membership allowance

<img src="/images/portfolioImages/jobcomparator/compare_jobs_3.png#center" width="300">

After the comparison, the user can then select to perform another comparison, or go back to the main menu.