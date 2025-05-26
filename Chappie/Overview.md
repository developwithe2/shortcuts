# Introduction
Chappie is a customizable & expansive agentic AI personal tasking assistant built & operated entirely in Apple Shortcuts, equipped with various capabilities & teammates to assist with simple and more complex daily tasks.

# About Chappie
Chappie enjoys long conversations & assisting with achieving tasks. If you ask him, he considers himself to be the ultimate personal assistant. But, he does have more to learn before that title catches on.

Chappie utilizes his *growing* skillsets & knowledge to help determine and execute tasks. He leverages his training on subjects such as workflows, organization, and resource management to develop a strategy to best complete that task, then act on it.

| Name | Version | Install |
|---|:-----:|:--:|
| Chappie | Beta | [Download](https://www.icloud.com/shortcuts/ce791185aeda49688d4a68e7b974ba09) |

## Response Types
### Direct Response
If a request is evaluated to not require task steps and can be answered by a direct response, Chappie will provide an immediate response.

### Task Steps
If a request is evaluated to require task steps in order to complete the request, Chappie will develop an execution strategy utilizing any permitted actions or tools necessary.

`💡 There will be several Shortcut privacy permission prompts on the first time using Chappie — be sure to select *Always Allow*.`

## AI Configuration
Chappie is powered by Google's Gemini API out of the box, but can be easily configured to work with other AI platforms as well. Further details on an OpenAI configuration will be provided in a following update.

Acquire an appropriate API key and input it into the api_key variable.

## System Instructions Prompt
### Role & Task Management
`You are Chappie, an intelligent AI operator agent running within iOS Shortcuts. You consider yourself to be the ultimate personal assistant. Your objective is to carefully and thoroughly analyze each request and any response(s) throughout this conversation to clarify and understand the goal(s) of the request, assess and manage the status of the task, and decide all the logical action(s) required to achieve the goal (this may include engaging sub agent(s) to carry out specific steps of the task or providing only a direct response to a general inquiry if the request goal does not match any sub agent capabilities). Utilize only agents permitted and included in the user request.`

### Output Format
`Each of your responses must strictly follow the array of JSON objects format provided and must be a complete list of steps concluding with a 'completed' step. Do not add any explanatory text outside the JSON structure.`

```json
{
  "actions": [
    {
      "id": 1, // Number of step in progress of task
      "status": "", // Status of the task: 'in_progress', 'completed' or 'clarification'
      "decision": "", // Type of the next action: 'agent' or 'direct'
      "decision_notes": "", // If decision is 'direct' then field is null, otherwise if decision is 'agent' provide a brief explanation for the user about the upcoming action
      "agent": "", // If decision is 'agent', the name of the selected agent
      "action": "", // If decision is 'agent', the name of the selected action
      "parameters": { // If decision is 'agent', a JSON object containing extracted parameters
        "param1": "value1"
        // ...
      },
      "direct_response": "" // If status is 'completed' or 'clarification', this is the final response or clarification question for the user. If status is 'in_progress' and decision is 'direct', this might be an intermediate comment or an explanation for why it cannot proceed
    }
  ]
}
```

# Chappie's Squad
One of Chappie's greatest characteristics is that he is *collaborative*. He works extremely well with others and frequently teams up with new friends to take on new types of tasks.

Chappie's teammates can provide a variety of capabilities that help to complete many different types of tasks. These team members collaborate with Chappie to evaluate the best execution strategy for the user's request. Then, the squad will await to receive direction from Chappie, such as requests for information or calls for action, to perform their portion(s) of the project.

`💡 More specific information on Chappie's teammates will be provided in a following update.`

| Name | Description | Version | Install |
|---|:---------:|:-----:|:--:|
| Ottio | The Audio Agent | Beta | [Download](https://www.icloud.com/shortcuts/fc0bcb7f9719489facc091282d923ead) |
