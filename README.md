# ASA-HBC
 



## General Instruction

Each request consists of three components: context, tasks, and output format. The context provides relevant information for the given task, which is then instructed to the Language Model (LLM) for execution. The output format is determined based on the context information and task, ensuring the appropriate presentation of results in structured text, tables, or plain text. Each task has its unique format, and the context provides different information, such as database details or user input, according to specific requirements.


The following section provides an explanation of each type of requests performed by the Language Model (LLM) and highlights their respective utilization within the behavior change support system.


A very general format:

```
Context:
	<dataset1> :
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	<dataset2> :
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		.
		.
		.
	<datasetn> :
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>		
	<external_input1> :
		<input_in_desired_format>
	<external_input2> :
		<input_in_desired_format>
Task:
  	<chatbot role><context instruction for {prompt_id} > <main instruction for {prompt_id}>
Output Format:
 	<output format for {prompt_id}>
   
```


We have two example profiles of working of the system. The examples of both personas for each task is given below.  
Persona 1 is of 30 years old female with "Achieving Healthy Weight" Goal and persona 2 is of 55 years old male with "Stress Management" Goal.

For All the queries, <chatbot role> is: *"you are a part of health behaviour change support system."*

Note: for the sake of simplicity, User Health Profile and User Profile will be mentioned as User Profile. 

## LLM Requests

### Generate Assesment Questionnaire

#### Objective:
Here the aim is to construct a comprehensive questionnaire designed to populate the various datasets as articulated in the Data Model, which includes Users, Health Profile, User Goal, Goal Observations, and Behaviour Determinants. 

#### Context:
This pertains to entries within the dataset where there are missing fields that require information. If a reference dataset is needed to locate this missing information, this should also be considered.

#### Output Format:
The questionnaires generated will be diverse in nature, their design being guided by the context and the ultimate objective. 

#### Structure of the LLM Query:

```
Context:

	<dataset1> :
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	<dataset2> :
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
  
Task:

  	<chatbot role><context instruction for {prompt_id} > <main instruction for {prompt_id}>

Output Format:

 	<output format for {prompt_id}>
   
```


#### Application Scenarios
 
Asking questionnaire for obtaining:

+ Initial missing information in User_Profiles Dataset (*[Context]: User_Profiles dataset ; [Output Format]: list of questionnaire* )
+ Initial missing information in Goals dataset (*[Context]: Goals dataset ; [Output Format]: list of questionnaire* )
+ Initial missing information in Goal_Observations dataset (*[Context]: Goal_Observations dataset ; [Output Format]: list of questionnaire* )
+ information for User_Change_Determinants dataset based on Goals dataset (*[Context]: Goals dataset, User_change_behaviour dataset ; [Output Format]: multiple choice questionnaire questionnaire* )
+ User goal assesment

#### Examples 


##### [User_Profiles Dataset]([https://chat.openai.com/share/cb706526-1871-442e-9846-ce75e224a626](https://chat.openai.com/share/821ded02-3d93-4204-b2a2-bd6f17f7b4a0)):

###### Persona 1:
![task1_health_profile_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v4/profile_questionnaire11.png) 
![task1_health_profile_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v4/profile_questionnaire12.png) 

###### Persona 2:
![task2_health_profile_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v4/profile_questionnaire21.png) 
![task2_health_profile_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v4/profile_questionnaire22.png) 

##### [Goal and Goal_Observations Dataset](https://chat.openai.com/share/23e0acfc-d207-4e90-8415-f994faf57d38):

###### Persona 1:
![task1_goal_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure_questionnaire11.png)
![task1_goal_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure_questionnaire12.png)


###### Persona 2:
![task2_goal_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure_questionnaire21.png)
![task2_goal_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure_questionnaire22.png)



##### [Behaviour_determinants Dataset](https://chat.openai.com/share/66e3dced-2129-4a03-aa57-f6b525aff8e5):

###### Persona 1:
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire11.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire12.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire13.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire14.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire15.png)



###### Persona 2:
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire21.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire22.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire23.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire24.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire25.png)
![task1_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/BD_questionnaire26.png)

### Request for Recommendation / Classification

#### Objective:
In this task we build an intelligent information analyzer and generator with the intent of delivering recommendations or classifying provided data into predefined categories. This system operates by accepting contextual information as an input and generating fitting text output in line with the assigned task.

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

   	<chatbot role><context instruction for {prompt_id} > <main instruction for {prompt_id}>

Output Format:

   	<output format for {prompt_id}>  
```


#### Application Scenarios

+ **Behaviour Goal Identification** : Identifying three best possible goals after updating  User_Profiles dataset (*[Context]: User_Profiles dataset ; [Output Format]: list of names*)
+ **Goal Measures Identification** : After user selects a goal, identifying three best measures of that goal based on goal name and goal description. (*[Context]: Goals dataset ; [Output Format]: colon separated structured text*)
+ **Stage of Change Identification** : Identifying current value of user's  behaviour determinant Stage of Change (precontemplation/contemplation/preperation/action/maintainance) based on User_Profiles, User_Goal, Goal_Observations, User_Change_Determinants datasets information (*[Context]: User_Profiles, User_Goal, Goal_Observations, User_Change_Determinants datasets ; [Output Format]: class name*)

#### Examples

##### [Behaviour Goal Identification](https://chat.openai.com/share/b98cdfa4-22a4-4c5e-a105-b7a635044fd5)

###### Persona 1:
![task2_health_goal_identification_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_selection11.png)
![task2_health_goal_identification_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_selection12.png)


###### Persona 2:
![task2_health_goal_identification_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_selection21.png)
![task2_health_goal_identification_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_selection21.png)
 

##### [Goal Measures Identification](https://chat.openai.com/share/7d06e712-48e4-4a94-9165-be1eb07174c0)

###### Persona 1:
![task2_goal_measure_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure11.png)
![task2_goal_measure_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure12.png)


###### Persona 2:
![task2_goal_measure_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure21.png)
![task2_goal_measure_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v3/goal_measure22.png)



##### [Stage of Change Identification](https://chat.openai.com/share/4300e44f-24e1-4cfb-98f4-02bc8b2fff70)

###### Persona 1:
![task2_change_stage_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task2_stagechange_1.png)

###### Persona 2:
![task2_change_stage_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task3_stagechange_1_p2.png)





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

   	<chatbot role><context instruction for {prompt_id} > <main instruction for {prompt_id}>

Output Format:

   	<output format for {prompt_id}>
```


#### Application Scenarios
Based on answers of the questionnaires
+ Filling Behaviour_Determinants dataset for a particular goal  (*[Context]: Behaviour_Determinants dataset, User_Response ; [Output Format]: colon separated list*)
+ Filling Health_Profile dataset (*[Context]: Health_Profile dataset ; [Output Format]: colon separated list*)
+ Filling User_Goal dataset (*[Context]: User_Goal dataset ; [Output Format]: colon separated list*)
+ Filling Goal_Observations dataset (*[Context]: Goal_Observations dataset ; [Output Format]: colon separated list*)
+ Filling Users dataset (*[Context]: Users dataset ; [Output Format]: colon separated list*)

#### Examples

##### [Behaviour_Determinants dataset](https://chat.openai.com/share/0e721d92-e6e5-49b5-94b0-d8db18cb9060)

###### Persona 1:
![task3_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task3_bd_1.png)
![task3_behaviour_determinants_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task3_bd_2.png)



###### Persona 2:
![task3_behaviour_determinants_p1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task3_bd_1_p2.png)
![task3_behaviour_determinants_p2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task3_bd_1_p2.png)


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

	User_Profiles:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	User_Change_Determinants:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Goals:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Goal_Obervations:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		
Task:
       
       <chatbot role><context instruction for {prompt_id} ><task1 instruction for identifying CALO-RE techniques><task2 instruction for designing weekly plan><task3 instruction for generalized BCT plan>

Output Format:

       <output format for {prompt_id}>  
```


#### Application Scenarios
+ initial plan generation based on initial dataset values

#### [Example](https://chat.openai.com/share/eaf0b536-2733-4476-8d3d-2f3af6a7046b)

###### Persona 1:

![task4_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_1.png)
![task4_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_2.png) 
![task4_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_3.png)
![task4_4](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_4.png) 
![task4_4](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_5.png) 


###### Persona 2:

![task4_1p](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_1_p2.png)
![task4_2p](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_2_p2.png) 
![task4_3p](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_3_p2.png)
![task4_4p](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_4_p2.png) 
![task4_5p](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_5_p2.png) 

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

	User_Profiles:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	User_Change_Determinants:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Plan_Entry:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		
Task:
       
       <chatbot role><context instruction for {prompt_id} > <main instruction for {prompt_id}>

Output Format:

       <output format for {prompt_id}>  
       
```


#### Application Scenarios
+ Executing text generation intervention plans based on plan_entry as per requirement


#### [Example](https://chat.openai.com/share/3753d795-8967-49ef-a7d9-42b5181c375a)

###### Persona 1:
![task5_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task5_1.png)
![task5_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task5_2.png)

###### Persona 2:
![task5_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task5_1_p2.png)
![task5_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task5_2_p2.png)




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


	Behaviour_Change_Plan:
		<attribute_name1> ; <attribute_name2> ;.... <attribute_namen> 
		<row1_value1> ; <row1_value2> ; ... <row1_valuen>
		<row2_value1> ; <row2_value2> ; ... <row2_valuen>
		.
		.
		.
		<rown_value1> ; <rown_value2> ; ... <rown_valuen>
		
	<feedback type> :
		<feedback>
	
	User_Profiles:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	User_Change_Determinants:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>	
	Goals:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
	Goal_Obervations:
		<field_name1> : <value1> ;<field_name2> : <value2>;...... <field_namen> : <valuen>
		
Task:
       
       <chatbot role><context instruction for {prompt_id} > <main instruction for {prompt_id}>

Output Format:

       <output format for {prompt_id}>  
       
```


#### Application Scenarios

 Modifying existing plan based on
 + User feedback
 + Behaviour Scientist Feedback
 + Goal Assesment Feedback

#### [Examples](https://chat.openai.com/share/5b9a4947-9844-43c2-8738-8d4bc315f18a)

###### Persona 1:

***User Feedback**: This plan is very regorous for me. suggest a bit easy plan.*

![task6_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_1.png)
![task6_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_2.png)
![task6_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_3.png)


***Behaviour_Scientist_Feedback**: Plan is not increamental. gradually increase difficulty.*  

![task6_s11](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s1_1.png)
![task6_s12](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s1_2.png)
![task6_s13](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s1_3.png)

***System_Generated_Feedback**: user is not able to follow eating healthy plan. they are not able to even walk for 10 minutes a day.*  

![task6_s21](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s2_1.png)
![task6_s22](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s2_2.png)

###### Persona 2:

***User_Feedback**: I can not have social gatherings more than once in a week.* 

![task6_s31](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s3_1.png)
![task6_s32](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s3_2.png)
![task6_s33](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s3_3.png)

***Behaviour_Scientist_Feedback**: some specificity required in exercises for deep breathing or knee exercise.*	
***User_Feedback**:I can not have social gatherings more than once in a week.*

![task6_s41](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s4_1.png)
![task6_s42](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s4_2.png)
![task6_s43](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s4_3.png)

***System_Generated_Feedback**: User is able to follow meditation plan and breathing exercises. however yoga classes are not attended by user. Also uder could not follow calling friends and spendint time with family tasks.*

![task6_s51](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s5_1.png)
![task6_s52](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s5_2.png)
![task6_s53](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task6_s5_3.png)



### Examples showing customization

#### [Customization in Behaviour Change Plan](https://chat.openai.com/share/e729af43-6e5d-4924-97b0-073c0284d976)

One modification has been made to the previously mentioned health profile of persona 1 in this example. Specifically, the individual's health condition now includes the fact that one leg has been amputated and they are handicap. As a result, the recommendations for physical activity have shifted from walking to exercises suitable for wheelchair users. 

![task4_s1_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_s1_1.png)
![task4_s1_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_s1_2.png)
![task4_s1_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_s1_3.png)
![task4_s1_4](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task4_s1_4.png)

#### [Customization in Stage of Change]()
By changing either user change determinants, user profile or goal measures, one's stage of change also gets modified. This examples are of persona 2 profile. Below are different scenarios where some information in context is changed that led to change in stage of change of the user. Original stage of change of the user is *Action.*


[*modification: ”stress eating” is added in eating pattern in previous profile -> Preperation*](https://chat.openai.com/share/620bf8df-7111-4d56-bac4-ecd0920f5b6e)
![task4_s1_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task2_s1_1.png)

[*modification: current Goal Measurement values are downgraded by huge amount -> Preperation*](https://chat.openai.com/share/798f4021-5ac6-4241-bb0f-4c51a26dffc7)
![task4_s1_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task2_s1_2.png)

[*modification: values of other User Change Determinants change -> Preperation*](https://chat.openai.com/share/a36caa08-4441-40ac-b4d6-cd0e99527c07)
![task4_s1_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task2_s1_3.png)

[*modification: All above -> Contemplation*](https://chat.openai.com/share/a36caa08-4441-40ac-b4d6-cd0e99527c07)
![task4_s2_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_v2/task2_s2_1.png)





<!---
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

##### Behaviour_Determinants dataset

![task3_behaviour_determinants_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task3_behaviour_determinants_1.png)
![task3_behaviour_determinants_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task3_behaviour_determinants_2.png)


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

#### Example

##### Query:

![task4_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_1.png)
![task4_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_2.png) 

##### Response:
![task4_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_3.png)
![task4_4](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_4.png) 
![task4_5](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_5.png)



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


#### Example

##### Query:
![task5_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task5_1.png) 
![task5_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task5_2.png)

##### Answer:
![task5_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task5_3.png) 




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

##### User feedback

**Example1**

![task6_s1_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s1_1.png) 
![task6_s1_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s1_2.png)
![task6_s1_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s1_3.png) 


![task6_s1_4](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s1_4.png) 

**Example2**

![task6_s2_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s2_1.png)
![task6_s2_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s2_2.png) 

##### Behaviour Scientist Feedback

![task6_s3_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s3_1.png) 
![task6_s3_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s3_2.png)

##### Goal Assesment Feedback

![task6_s4_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s4_1.png) 
![task6_s4_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task6_s4_2.png) 




### Examples showing customization

#### Customization based on health condition written in the Health_Profile

One modification has been made to the previously mentioned health profile in this example. Specifically, the individual's health condition now includes the fact that one leg has been amputated and they are unable to walk. As a result, the recommendations for physical activity have shifted from walking to exercises suitable for wheelchair users. Additionally, the behavior change technique has been adjusted from graded task to social support, taking into account the person's condition.

![task4_s2_1](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_s2_1.png)
![task4_s2_2](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_s2_2.png)
![task4_s2_3](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_s2_3.png)
![task4_s2_4](https://github.com/mhb3194/HICSS_Data/blob/main/images_LLM/task4_s2_4.png)

#### Customization based on state of change



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

