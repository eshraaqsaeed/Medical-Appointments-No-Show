# Medical-Appointments-No-Show
This project was implemented during the Udacity FWD Data Analysis Nanodegree Program

## Project Outlines:

###  Investigation questions:
- Q1: Which certain gender show more commitment to their medical appointment that the other?
- Q2: Does patient's age correlate with them showing up to the appointment?
- Q3: Does the patient's Scholarship availability affect their decision to attend their medical appointment?
- Q4: Does patient's disease affect their decision to appear to the appointment?
- Q5: Most requent neighborhood, and day for appointments and scheduling?
- Q6: Duration between scheduling and appointment days, in terms of: minimum, maximum, etc..?


## Data Cleaning

The dataset didn't require much handeling, as no missing values, nor duplicates, etc.. were found.

Some minor issues was detected:
- Issue 1: Some column names needs handling -> re-formated for neat and easy work
- Issue 2: Data types of some attribute
    - Patient_ID is float -> converted to string
    - Appointment_ID is int -> converted to string
    - ScheduledDay and AppointmentDay are strings -> converted to datetime format
- Issue 3: Age attribute has negative values


## Exploratory Data Analysis


#### Distribution of Dependent Variable (No_Show)

- With counts:
![no-show_distribution](https://user-images.githubusercontent.com/82108743/167433487-b6c55ef9-d20c-4825-a818-29b388fb6bfd.png)

- With percentages:
![show_to_no-show_ratio](https://user-images.githubusercontent.com/82108743/167433835-00db44e0-ec92-44d8-b4ba-735619338356.png)


#### Distribution of Gender
![gender_ratio](https://user-images.githubusercontent.com/82108743/167433682-68434be2-bb35-43f1-abff-0bfe11fb9e79.png)

##### Insights:
> Accordingly to the above figure, it is detectable that Female patients represent more than 50% of the data. Hence why, we need precise measuring when it comes to patient's gender

### *Q1*: Which certain gender show more commitment to their medical appointment that the other?

- Cross tabulation of gender againtst No-Show variable:

  | **No-Show/Gender**      | **No**      | **Yes**      |
  |------------|-------------|-------------|
  | **F** | 0.796851 | 0.203149 |
  | **M** | 0.800321 | 0.199679 |

![gender_no-show_crosstab](https://user-images.githubusercontent.com/82108743/167435101-e96d6a96-220f-4746-b9cd-e01da0fdabeb.png)

### *Q2*: Does patient's age correlate with them showing up to the appointment?

- Age distribution
![age_distribution](https://user-images.githubusercontent.com/82108743/167435787-4717ae54-06a2-49a7-bd2e-7beb938a0d0d.png)

- Age & Appointment commitment distribution
![age_no-show_correlation](https://user-images.githubusercontent.com/82108743/167435916-40f6531a-4d1e-4cc2-9848-f5fcd0b0e28d.png)

### *Q3*: Does the patient's Scholarship availability affect their decision to attend their medical appointment?

![scholarship_ratio](https://user-images.githubusercontent.com/82108743/167436128-ec36ec8a-cf19-46f3-9d46-d1e29cdacf48.png)

- Cross tabulation of scholarship against No-Show variable:

  | **No-Show/Scholarship**      | **No**      | **Yes**      |
  |------------|-------------|-------------|
  | **0** | 0.801926 | 0.198074 |
  | **1** | 0.762637 | 0.237363 |

**Patients with schoalrship:**
- Around 80% of these patients attend their appointment
- 19% of them didn't show up

**Patients without schoalrship:**

- Around 76% of these patients attend their appointment
- Around 23% of them didn't show up

### *Q4*: Does patient's disease affect their decision to appear to the appointment?

- **Diabetes**:
> 7.18% of patients have diabetes

- Cross tabulation of diabetic/non-diabetic against No-Show variable

  | **No-Show/Diabetes**      | **No**      | **Yes**      |
  |------------|-------------|-------------|
  | **0** | 0.796370 | 0.203630 |
  | **1** | 0.819967 | 0.180033 |

- **Hypertension**:
> 19.7% of patients have hypertension

- Cross tabulation of patients with/without hypertension

  | **No-Show/Hypertension**      | **No**      | **Yes**      |
  |------------|-------------|-------------|
  | **0** | 0.790961 | 0.209039 |
  | **1** | 0.826980 | 0.173020 |

- **Alcoholism**:
> 3% of patients are alcohol addicts

- Cross tabulation of patients addicted/un-addicted to alcohol

  | **No-Show/Alcoholism**      | **No**      | **Yes**      |
  |------------|-------------|-------------|
  | **0** | 0.798052 | 0.201948 |
  | **1** | 0.798512 | 0.201488 |

### *Q5*: Most requent neighborhood, and day for appointments and scheduling?

- Dataset contained 81 different neighbourhoods
- The top 3 frequent neighbourhoods in appointments and scheduling:
![top3_neigh](https://user-images.githubusercontent.com/82108743/167437137-1b4c7c89-bf8e-4067-9553-c22c6ca60709.png)

> #### Most frequent day for appointment and scheduling:
![most_freq_days](https://user-images.githubusercontent.com/82108743/167437371-cbe60368-dd6d-4447-9d3a-3b9c29ee83bb.png)

> Most frequent day for scheduling is **Tuseday**

![most_frew_days_appoint](https://user-images.githubusercontent.com/82108743/167437340-e65e2ead-53b8-419b-bf3f-31ebb7c9d8c4.png)
> Most frequent for appointments is **Wednesday**

We can also detect that **Saturday** is the least frequent day for both scheduling and appointments.

### *Q6*: Duration between scheduling and appointment days, in terms of: minimum, maximum, etc..?

- Minimum waiting time = 0 days with 38562 patients
- Maximum waiting time = 179 days with 10 pateints
- 
> **That alot!!** A patient might wait for 179 days to get their appointment! Fortunately, it present rarely in the data, which means it's not the usual situation in appointments duration.

Now lets see if patient/s who waited this long, ended up attending their medical appointment of not? and vise versa, did patients who got immediate appointment, ended up commiting to their appointment?

![attending_lone_wait](https://user-images.githubusercontent.com/82108743/167438573-dc181707-8a4f-46db-b20f-d80e38e5515c.png)

- There are 10 patients who waited 179 days to attend their appointment.
- Among these patients, 80% of them attended their medical appointment despite the long wait, and 20% tend to not show up to the appointment.

Now lets see if patients who get immediate scheduling commit to their appointment:
![attending_immediate](https://user-images.githubusercontent.com/82108743/167438867-acecb9f3-e2e0-4cf5-8029-11c867d802ec.png)

We can finally say that, the average waiting time for patients to get their appointments is 10 days, 4 hours, and 24 minutes.

## Conclusions:

#### After performing the analysis, few exsiting insights were learned!

1. 79.8% of patients showed up to their appointmens, and 20.2% didn't attend.
2. Both female and male patients has almost the same commitment to attend their medical appointment.
3. Most of the patients is of a young age
4. Most of the patients do not hold a scholarship with percentage of 90.2%. While, 9.8% of the patients hold a scholarship. Both of these sections show almost similar commitment to their appointments.
5. 7.18% of patients have diabetes: 81.9% of them showed up to their appointment, while, around 18% of them didn't attend.
6. 19.7% of patients have hypertension: 82.6% of them showed up to their appointment, while, 17.3% of them didn't attend.
7. 3% of patients are alcoholism: 79.8% of them showed up to their appointment; while, 0.2% of them didn't attend.
8. Top 3 neighbourhoods frequently presented.
9. Most frequent day for scheduling is Tuseday.
10. Most frequent for appointments is Wednesday.
11. Most patients patients might wait for a few seconds, or even get the appointment immediately.
12. A patient might wait for 179 days to get their appointment! Fortunately, it present rarely in the data, which means it's not the usual situation in appointments duration. Despite that, 80% of them show up to their appointments.
13. The average waiting time for patients to get their appointments is 10 days, 4 hours, and 24 minutes.

##### phew! This wasn't a few!:monocle_face:
