Product: Shopify Business Scenarios

Environment Setup:

 - 	Download and initialize ESB 4.8.1 .
	Deploy relevant patches, if applicable and the ESB should be configured as below.
	Please make sure that the below mentioned Axis configurations are enabled in "<ESB_HOME>/repository/conf/axis2/axis2.xml".
		<messageFormatter contentType="text/javascript"
                        class="org.apache.synapse.commons.json.JsonStreamFormatter"/>						  
		<messageBuilder contentType="text/javascript"
                        class="org.apache.synapse.commons.json.JsonStreamBuilder"/>	
	
 
 - Upload the following connectors to the ESB.
 			-> redmine-connector-1.0.0
			-> linkedin
			-> gmail
 			-> surveymonkey
			
			
 - Follow the instructions given in the developer guide of above connectors, and enable the ESB axis configurations accordingly. Developer guide locations of aforementioned connectors are listed below.
	 		Redmine - https://docs.wso2.com/display/CONNECTORS/Redmine+Connector
 			Linkedin - https://docs.wso2.com/display/CONNECTORS/LinkedIn+Connector
			Gmail - https://docs.wso2.com/display/CONNECTORS/Gmail+Connector
           		SurveyMonkey - https://docs.wso2.com/display/CONNECTORS/SurveyMonkey+Connector
			
 - Add the corresponding website security certificates to the ESB for above mentioned connectors. 

 - Add the sequences and templates in the "common" directory (redmine-integrated-scenarios/src/common ), to the ESB.  
 
 - Each scenario folder is consisted of sub-folders named as <Case-xxx>. In order to execute a particular case, upload the corresponding proxy and the template files which reside in sub-folders, into the ESB.
		  
Scenarios in Brief:   


- AddingProjectMember
  
	Case-001 ->
			Scenario Name: 	Creating project member
			Description: 	Add a project member in redmine, then send survey request to the member and post about the membership on linkedin.						   
	Case-002 ->
			Scenario Name: 	Sending survey
			Description: 	Retrieves survey result from survey monkey, then send mails to the assignees.						   
