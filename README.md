# ASA-HBC
 



## General Instruction

Each request consists of three components: context, tasks, and output format. The context provides relevant information for the given task, which is then instructed to the Language Model (LLM) for execution. The output format is determined based on the context information and task, ensuring the appropriate presentation of results in structured text, tables, or plain text. Each task has its unique format, and the context provides different information, such as database details or user input, according to specific requirements.


The following section provides an explanation of each type of requests performed by the Language Model (LLM) and highlights their respective utilization within the behavior change support system.



## LLM Requests


### Generate Assesment Questionnaire

#### Objective:
Our aim is to construct a comprehensive questionnaire designed to populate the various datasets as articulated in the Data Model, which includes Users, Health Profile, User Goal, Goal Observations, and Behaviour Determinants. To do this, we need to extract the necessary information from the user.

#### Context:
This pertains to entries within the dataset where there are missing fields that require information. If a reference dataset is needed to locate this missing information, this should also be considered.

#### Output Format:
The questionnaires generated will be diverse in nature, their design being guided by the context and the ultimate objective.

#### Structure of the LLM Query:

```
Context:

	<dataset1>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	<dataset2>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
  
Task:

   <instruction for chatbot role><instruction for context><instruction for questionnaire generation>

Output Format:

   <instruction for output>
   
```


#### Application Scenarios
 
Asking questionnaire for obtaining:

+ Initial missing information in Users Dataset
+ Initial missing information in Health_Profile Dataset
+ Initial missing information in User_Goal dataset
+ Add information in User_Goal dataset
+ Add information in Goal_Observations dataset
+ Add information in Behaviour_determinants dataset based on User_Goal dataset
+ User goal assesment

#### Examples

##### User Dataset:
![task1_user_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task1_user_1.png)  

##### Health_Profile Dataset:
![task1_health_profile_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task1_health_profile_1.png) 

##### Goal and Goal_Observations Dataset:
![task1_goal_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task1_goal_1.png)
![task1_goal_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task1_goal_2.png)

##### Behaviour_determinants Dataset:
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task1_behaviour_determinants_1.png)
![task1_behaviour_determinants_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task1_behaviour_determinants_2.png) 

### Request for Recommendation / Classification

#### Objective:
We endeavor to build an intelligent information analyzer and generator with the intent of delivering recommendations or classifying provided data into predefined categories. This system operates by accepting contextual information as an input and generating fitting text output in line with the assigned task.

#### Context:
The context encapsulates the dataset entries which must be analyzed in order to generate the requisite text information.

#### Output Format:
The output format is variable, adapting to the type of information requested. This may take the form of structured text, tables, or specific class names.

#### Structure of the LLM Query:

```
Context:

	<dataset1>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	<dataset2>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
Task:
       
       <instruction for chatbot role><instruction for context><instruction for generating required text information>

Output Format:

       <instruction for output>   
```


#### Application Scenarios

+ **Behaviour Goal Identification** : Identifying two best possible goals and their one liner description after updating Users and Health_Profile datasets (*[Context]: Users dataset, Health_Profile dataset ; [Output Format]: table*)
+ **Goal Measures Identification** : After user selects a goal, identifying three best measures of that goal based on goal name and goal description. (*[Context]: User_Goal dataset ; [Output Format]: colon separated structured text*)
+ **Stage of Change Identification** : Identifying current value of user's  behaviour determinant Stage of Change (precontemplation/contemplation/preperation/action/maintainance) based on Users, Health_Profile, User_Goal, Goal_Observations, Behaviour_Determinants datasets information (*[Context]: Users dataset, Health_Profile dataset, User_Goal dataset, Goal_Observations dataset, Behaviour_Determinants dataset ; [Output Format]: class name*)

#### Examples

##### Behaviour Goal Identification

![task2_health_goal_identification_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task2_health_goal_identification_1.png)
 

##### Goal Measures Identification
![task2_goal_measure_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task2_goal_measure_1.png)


##### Stage of Change Identification
![task2_change_stage_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task2_change_stage_1.png)
![task2_change_stage_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task2_change_stage_2.png)




### Process User Input

#### Objective:

The aim of this task is to process and convert the responses received from users, as part of the questionnaire, into a desired dataset format. If a response is textual, it must be appropriately summarized and formatted. This Language Model (LLM) task involves the analysis of user responses and structures them into the required dataset format, ultimately outputting the completed dataset in the required format.

#### Context:

The context revolves around the dataset format, which includes the value options for each field, as well as the user output that is provided in a dataset format which needs to be populated into the intended dataset.

#### Output Format:

The output will be a table that displays the completed dataset.


#### Structure of the LLM Query:

```
Context:

	<current query database>
		<field_name1(field_format1)>: <existing_field_value1>; <field_name2(field_format2)>: <existing_field_value2>;........ <field_name3(existing_field_format3)>: <field_value2>
	<response from user>
		response_field_format1 ; response_field format2 ; ...... response_field format3
		
Task:
       
       <instruction for chatbot role><description of context><instruction for structuring answers of user response for query dataset><datasetwise field related instructions>

Output Format:

       <instruction for output>   
```


#### Application Scenarios
Based on answers of the questionnaires
+ Filling Behaviour_Determinants dataset for a particular goal  (*[Context]: Behaviour_Determinants dataset, User_Response ; [Output Format]: table*)
+ Filling Health_Profile dataset (*[Context]: Health_Profile dataset ; [Output Format]: table*)
+ Filling User_Goal dataset (*[Context]: User_Goal dataset ; [Output Format]: table*)
+ Filling Goal_Observations dataset (*[Context]: Goal_Observations dataset ; [Output Format]: table*)
+ Filling Users dataset (*[Context]: Users dataset ; [Output Format]: table*)

#### Examples

![]()
![]()
![]()
![]() 

### Plan Generation


#### Objective:
Once all relevant datasets, namely Users, Health_Profile, User_Goal, Goal_Observations, Behaviour_Determinants, are comprehensively populated, the next step involves creating a behavioral change plan to facilitate the achievement of set goals. For our purposes, we are adopting a standard timeline of one week for generating this behavioral change plan. The plan generation commences with the identification of appropriate behavioral change techniques(BCT), leveraging the CALO-RE Taxonomy for this purpose. There are three primary tasks assigned to the LLM in this plan generation phase. The first task is the selection of the three most suitable behavioral change techniques from the 40 identified in the CALO-RE Taxonomy] (https://www.dhi.ac.uk/san/waysofbeing/data/health-jones-michie-2011a.pdf), this selection is primarily based on the individual's stage of behavioral change. This approach is taken in light of the emphasis placed on tailoring behavioral change techniques according to the stage of behavioral change in [this paper] (https://www.researchgate.net/publication/349007558_Tailoring_Persuasive_and_Behaviour_Change_Systems_Based_on_Stages_of_Change_and_Motivation). The second task involves generating a week-long behavioral change plan, structured around the identified techniques, and segmented into morning, afternoon, and evening periods based on context information to make the plan personalised. The final task involves formulating a generalized daily rule for each selected behavioral change technique. This rule will serve two main purposes: 1) prompt the user to log their performance, and 2) motivate the user to engage in behavioral change activities. In second and third task, form of implementation of intervention is also provided which can be nudge, reminder, awareness message or questionnare. 
Once these plan is generated, its each entry is done in this Plan_Entry database. Also, entire plan is stored in the Plans dataset. Also, selected BCT are stored in plans dataset.  

#### Context:
The context involves the dataset entries pertaining to the user. These entries, drawn from the datasets Users, Health_Profile, User_Goal, Goal_Observations, and Behaviour_Determinants, will be used to generate the necessary text information.

#### Output Format:
The output for each task is structured in a tabular format, with predefined column names and layout.


#### Structure of the LLM Query:

```
Context:

	Users:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Health Profile:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Behaviour Determinants:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	User Goal:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Goal Obervations:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		
Task:
       
       <instruction for chatbot role><description of context><task1 instruction for identifying CALO-RE techniques><task2 instruction for designing weekly plan><task3 instruction for generalized BCT plan>

Output Format:

       <instruction for output>  
```


#### Application Scenarios
+ initial plan generation based on initial dataset values


### Reminder and Nudge Generation


#### Objective:
Once the plan is formulated and each component of the plan is recorded in the Plan_Entry dataset, it becomes necessary to generate specific intervention text at the corresponding execution time of each plan entry. This is dependent on the activity the user is expected to perform, the behavior change technique applied, and the form of intervention. To this end, Plan Entries, identified by their Entry_Id, along with other relevant user information are provided to the LLM as context. The LLM will then generate suitable intervention text associated with each Entry_Id.

#### Context:
The context encompasses dataset entries related to the user. The relevant information, drawn from the datasets Users, Health_Profile, User_Goal, Goal_Observations, Behaviour_Determinants and Plan_Entry, will be analyzed to generate the necessary intervention text.

#### Output Format:
The output is presented as a colon-separated list, comprising of the Entry_Id and the corresponding generated text intervention.

#### Structure of the LLM Query:
```
Context:

	Users:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Health Profile:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Behaviour Determinants:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Plan Entry:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		
Task:
       
       <instruction for chatbot role><description of context><instruction for creating form of intervention>

Output Format:

       <instruction for output> 
       
```


#### Application Scenarios
+ Executing text generation intervention plans based on plan_entry as per requirement


### Improve Plan Based on Feedback

#### Objective:
Throughout different stages of the behavior change support system, the generated plan may need to be modified based on various forms of feedback. This could be user feedback, gathered while the plan is being implemented throughout the week; feedback from behavior scientists for approval once the plan is generated; or goal assessment feedback, obtained at the end of each week. For this purpose, the existing plan is provided so that a new, modified plan can be generated based on the feedback received. Additionally, user-specific information from different databases is incorporated into the input, enabling the LLM to analyze it and generate a personalized plan based on the feedback. Plan_Entry dataset and Plans dataset is also modified based on new plan.

#### Context:
The context encompasses user-related information sourced from the datasets Users, Health_Profile, User_Goal, Goal_Observations, Behaviour_Determinants. Additionally, the current plan and feedback text are also included in the context.

#### Output Format:
The output is formatted as a table, mirroring the structure of the current plan.

#### Structure of the LLM Query:
```
Context:


	behaviour change plan:
		<attribute_name1> ; <attribute_name2> ;.... <attribute_namen> 
		<row1_value1> ; <row1_value2> ; ... <row1_valuen>
		<row2_value1> ; <row2_value2> ; ... <row2_valuen>
		.
		.
		.
		<rown_value1> ; <rown_value2> ; ... <rown_valuen>
		
	<feedback type> :
		<feedback>
	
	Users:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Health Profile:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Behaviour Determinants:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Plan Entry:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	User Goal:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Goal Obervations:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		
Task:
       
       <instruction for chatbot role><description of context><description of feedback type><instruction for generating new plan based on feedback type>

Output Format:

       <instruction for output>
       
```


#### Application Scenarios

 Modifying existing plan based on
 + User feedback
 + Behaviour Scientist Feedback
 + Goal Assesment Feedback

#### Examples



<!---
# Example 1


### Profile Generation from Seed Data

Here we have described a simulated persona of one Indian Female named Sita. 

Let us start system walk through from the time Sita registers into our ASA-HBC. Once registered, Sita is requested to provide access to any personalized self-written data. Sita provides access to Linkedin. Now, orchestrator generates message for behaviour assessment sub-system to use this data to generate profile information of Sita. Behaviour assessment sub-system extracts profile description from linkedin, and tasks LLM to extract structured profile information based on description. Figure shows query to LLM, output generated by LLM. This information is then stored in Users file in Datastore.

![Profile Generation from Seed Data](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/profile_generation_1.png)

### Profile Generation Questionnare

Next, we can see that some profile information like name, age, gender are not generated. Also health and life style information is not generated. Thus , next orchestrator generates message for behaviour assessment subsystem to generate query for missing health profile information. Figure 4 shows query to LLMs and response questionnaire provided by LLMs. 

![Profile Generation Questionnare](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/Profile_generation_2.png)


### User Profile Data

Below is the profile information provided by user and was structured by LLM to store in Users in datastore. 

![User Profile Data](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/user_profile_1.png) 

### User Goal Options Creation

 Now, based on all the profile information in data store, LLMs are tasked to determine possible goals for user. Figure 5 shows query and output of LLM for this task. 

![User Goal Options](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/goal_selection_1.png) 

### User  selected goal

User Selects below goal:

*Weight Management and Physicaltask1_behaviour_determinants_1 Activity: "Adopt a balanced diet and increase physical activity to manage BMI and enhance overall health."*

### Behaviour determinants questionnaire



#### Query

![determinant_query](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/behaviour_determinants_1_new_p1.png) 

#### Answer

![determinant_ans_1](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/behaviour_determinants_1_new_p2.png) 
![determinant_ans_2](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/behaviour_determinants_1_new_p3.png) 

#### Answer of the questionnaire from user

*I am not very much concerned about impact of BMI on my health, yes I think stress eating is a problem, but i dont think it is going to affect me in near future. I believe what I eat affects my healh. Taking balenced diet will surely healp to my not just physical but mental health. I am not at high health risk based on current BMI. My current life style is not that bad, that it can affect my work or personal life. Balanced diet is more important than physical activity for improving my health. I think if I will take balanced diet, I will feel more fresh, light and energetic. I think I will become more fit and attractive that will affect my social life and because of energy, I will feel more enthusiastic to work. Biggest obstacle is my erratic work schedule, my tendency to get afraid in starting new thing and not being able to be consistent on achieving difficult goal. Also my love for variety of food will also be a problem. I do not drink very much alcohol, thus no issue. There is no garden near my house. there is a lot of pollution around me. I am not confident nor I have tried making lifestyle changes in past. Yes, film stars motivate me sometimes, but it is shortlived. the daily reminder partner and some reward might help me to stay motivated.*


### Behaviour Determinants Extraction

#### Query

![determinant_extraction_query](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/behaviour_determinants_2_new.png)


#### Answer

![determinant_extraction_answer](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/behaviour_determinants_3_new.png)

### Goal Measurement

![goal_measurement](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/goal_measurement_1.png)

### Goal Targets given by user

![goal_targets](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/goal_targets.png)

### Intervention Plan Generation

#### Query

![intervention_query](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/Plan_generation_1.png)

#### Answer

![intervention_ans](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/Plan_generation_2.png)
![intervention_ans2](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/Plan_generation_3.png)
![intervention_ans3](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/plan_generation_4.png)

### Intervention Execution

#### Query

![intervention_exq1](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/interventions_1.png)
![intervention_exq2](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/interventions_2.png)


#### Answer

![intervention_exa](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/intervention_3.png)


### Goal Assesment

#### Query

![](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/goal_assesment_1.png)

### Answer

![](https://github.com/mhb3194/HICSS_Data/blob/main/LLM_Tasks/goal_assesment_2.png)



![]()
![]()
![]() 





( "")
( "")
( "")

--->

