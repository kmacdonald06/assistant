---

copyright:
  years: 2015, 2018
lastupdated: "2018-05-08"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Building a conversational skill
{: #create-convo-skill}

The natural-language processing for the {{site.data.keyword.conversationshort}} service is defined in a *conversational skill*, which is a container for all of the artifacts that define a conversation flow.
{: shortdesc}

## Skill limits
{: #skill-limits}

Currently, you can add one conversational skill to an assistant.

The number of skills you can create in a single service instance depends on your {{site.data.keyword.conversationshort}} plan. The sample skills do not count toward your limit unless you edit or duplicate them.

| Service plan     | Skills per service instance |
|------------------|----------------------------:|
| Premium          |                         100 |
| Standard         |                          20 |
| Lite*            |                           5 |
{: caption="Service plan details" caption-side="top"}

*After 30 days of inactivity, an unused Lite skill might be deleted to free up space.

## Creating a skill
{: #creating-skills}

You can create a skill from scratch, use a sample skill that is provided by IBM, or import a skill from a JSON file.

Follow these steps to create a conversational skill:

1.  Click the **Skills** tab.

    **Note**: If you created or were given developer role access to any workspaces that were built with the generally available version of the  {{site.data.keyword.conversationshort}} service (formerly Watson Conversation), you will see them listed as conversational skills.

1.  Do one of the following things:

    - To create a skill from scratch, click **Create new**.
    - To add a sample skill that is provided with the service as a starting point for your own skill or as an example to explore before you create your own, click **Add a sample**.

      The sample skill is added to your list of skills. It is not associated with any assistants. Skip the remaining steps in this procedure.
    - To import a skill from a JSON file, click the ![Import skill](images/workspace_import.png) icon, and select the JSON file you want to import from.

      **Important:**

      - The imported JSON file must use UTF-8 encoding.
      - The maximum size for a skill JSON file is 10MB. If you need to import a larger skill, consider importing the intents and entities separately after you have imported the skill.
      - The JSON cannot contain tabs, newlines, or carriage returns.

      Specify the data you want to include:

        - Select **Everything (Intents, Entities, and Dialog)** if you want to import a complete copy of the conversational skill, including the dialog.
        - Select **Intents and Entities** if you want to use the intents and entities from the conversational skill, but you plan to build a new dialog.

1.  Specify the details for the new skill:
    - **Name**: A name no more than 100 characters in length. A name is required.
    - **Description**: An optional description no more than 200 characters in length.
    - **Language**: The language of the user input the skill will be trained to understand. The default value is English.

After you create the skill, it appears as a tile on the Skills page. Now, you can start identifying the user goals that you want the assistant to address. See [Planning your intents and entities](intents-entities.html) for more details.

The conversational skill cannot interact with customers until it is added to an assistant and the assistant is deployed. You must open the assistant tile and add the skill to the assistant from the assistant configuration page; you cannot choose the assistant that will use the skill from within the skill configuration page. One skill can be used by more than one assistant.

## Downloading a skill
{: #download-skill}

You can download a skill in JSON format. You might want to download a skill if you want to use the same skill in a different instance of the {{site.data.keyword.conversationshort}} service, for example. You can download it from one instance and import it to another instance as a new skill.

To download a skill, complete the following steps:

1.  Find the skill tile on the Skills page or on the configuration page of an assistant that uses the skill.

1.  Click the ![open and close list of options](images/kabob-beta.png) icon, and then choose **Download JSON**.

1.  Specify a name for the JSON file and where to save it, and then click **Save**.

## Deleting a skill
{: #delete-convo-skill}

You can delete any conversational skill that you can access, unless it is being used by an assistant. If it is in use, you must remove it from the assistant that is using it before you can delete it.

Be sure to check with anyone else who might be using the skill before you delete it.
{: tip}

To delete a conversational skill, complete the following steps:

1.  Find out whether the skill is being used by any assistants. From the Skills tab, find the tile for the skill that you want to delete. The **Assistants** field lists the assistants that currently use the skill.

1.  If the skill you want to delete is associated with an assistant, then remove it from the assistant by completing the following steps:

    - Check with the owner of the assistant that is using the skill before you remove the skill from it.
    - Open the Assistants tab, and then click to open the assistant tile.
    - From the Skills section, find the tile for the skill that you want to delete. Click the ![open and close list of options](images/kabob-beta.png) icon, and then choose **Remove**.
    - Repeat the previous steps for any other assistants that are using the skill.
    - Return to the Skills tab and find the tile for the skill that you want to delete.

1.  Click the ![open and close list of options](images/kabob-beta.png) icon, and then choose **Delete**. Confirm the deletion.