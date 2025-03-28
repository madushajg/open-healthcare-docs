#Connecting EHR/EMR Systems

##Overview
WSO2’s solution offers out-of-the-box connectors for Health Care vendors such as EPIC, Cerner, and Athena Health EMRs and is capable of generating connectors automatically to any FHIR based or Open API  specificationbased EHR/EMR system.<br> These connectors will increase the developer's productivity by providing an abstraction to the EHR/EMR system endpoints, but are not a must for WSO2 to integrate with an EHR/EMR.<br><br> This section will provide instruction on how to obtain the EHR/EMR connectors, how to install them, and how to use them.

##Set up the required connectors
Follow the instructions given below to set up the connectors you require in your WSO2 Integration Studio.
<ul>
<li>    You can request a connector for any FHIR compliant EHR/EMR system, or a system that has an Open API specification.</li>
<li>    You need to provide the capability statement or the Open API specification.</li>
<li>    The internal tool will generate the required connectors upon feeding the artifacts provided.</li>
<li>    The connector zip file will be provided after it is generated by the tool.</li>
</ul>

##Install the connector
As mentioned in the previous section, WSO2 Integration Studio is the IDE that will be used to develop integrations that will be deployed in the integration layer of the Healthcare solution. The connector zip that is obtained from WSO2 should be imported to the Integration Studio in order to develop the integration flow.<br> Steps on installing and using the connector can be found by clicking the [link](https://apim.docs.wso2.com/en/4.0.0/reference/connectors/connectors-overview/#how-to-use-connectors)<br>

##Connect system to integration logic
In this section let’s walk through a simple example of connecting to the Epic EHR system and searching and retrieving some patient data. Epic is a FHIR compliant EHR system. WSO2 has a pre-built connector for the Epic sandbox environment. Let’s create a new Integration project and add a Rest API to it. More information on creating the integration project,and the Rest API can be found [here](https://apim.docs.wso2.com/en/4.0.0/integrate/develop/integration-development-kickstart/).<br>Then let's import the Epic connector to the Integration Studio as mentioned in the previous section. Once imported the mediator <strong>Palette</strong> of the Integration Studio will have the Epic connector listed. As shown in the below image


 <img src="../../../assets/img/guildes/configuring-ehr-emr-system/epic-in-palatte.png" width="500">

The required connector operations have to be dragged and dropped to the canvas. Once it is done, you can see a view similar to the above canvas. Next the Respond mediator will be added after the connector operations to return the response received from Epic to the client.


 <img src="../../../assets/img/guildes/configuring-ehr-emr-system/canvas.png" width="700">

The above image describes the user of the init and the searchPatient connector operations. When an operation is clicked the following property pane will be visible with all the parameters that the operation would accept.

 <img src="../../../assets/img/guildes/configuring-ehr-emr-system/property.png" width="700">

Above is the property pane for the init operation. Here it is important to pass the connection and authentication-related information like base URL, client ID, etc.

For the next operation, searchPatient, displayed by the following property pane has all the supported search parameters for the Patient FHIR resource by the Epic server.

<img src="../../../assets/img/guildes/configuring-ehr-emr-system/patient.png" width="700">

You can now fill in the required parameters. Once done, you can bundle the connector and integrate the project as mentioned [here](https://apim.docs.wso2.com/en/4.0.0/reference/connectors/connector-usage/#export-and-run-a-project-with-connectors)

