# Actors
  * **Employees:** Workers who want to better understand their stress level and possible causes of it. Also may be looking for a way to lower stress and cope with their emotions.

  * **Managers / HR employees:** Higher-level employees who want to analyze and target possible stressors in their workplace team to support employee morale.

  * **Executives:** Users who will be able to monitor employees/managers, create surveys, and generally manipulate the system.

# Use Cases
  * UC1: Access visualized biometric data post-simulation (Actors: Employee)
    * After engaging in the VR simulation, an employee can access a data visualization app that will give a summary of various biometric values collected by the headset, including heart rate, eye gaze/pupil dilation, and cognitive load. 
    * Program flow:
      1. Data is sent from the HP SDK through the AWS data API
      2. Request handler passes it along to the data handling interface  
      3. Once processed, the visualiztion interface displays the data in a well-polished UI experience within the headset
    * Corresponding business requirement: BR3

  * UC2: Access visualized employee mental health/stress levels (Actors: Managers, Executives)
    * Using the Peak Mind webapp, managers can create comprehensive visual reports that aggregate the surveys and feedback data received from employees (i.e. what most urgently needs to be improved in the work environment). With the user's permission, biometric data is sent back through the AWS API and is also accessible by managers and executives, enhancing the survey data. 
    * Program flow:
      1. Data is stored from user surveys in webapp or VR biometric data interface
      2. Manager selects timeframe or specific employees and initiates the report creation
      3. Specified data is passed through visualization interface and report is displayed
      4. Manager can choose to save report if further analysis is needed
    * Corresponding business requirements: BR1, BR2

  * UC3: Privacy touchpoints for surveys and general feedback (Actors: Employees, Managers)
    * When using the Peak Mind dashboard webapp, users have the ability to complete surveys regarding stress levels and also send in general feedback in case they just need to vent. Employees can to control who sees this data and if their name is attached to it through a dialogue box that allows them to specify between management, the HR department, or an anonymous submission.
    * Program flow:
      1. User completes survey, or fills out feedback box
      2. Webapp prompts user to choose visibility of their data (management, HR, anonymous submission)
      3. Data is sent to managers/executives and is accessible to create visualized reports regardless of privacy level
      4. Usage statistics on the privacy touchpoints are made available to managers and executives

