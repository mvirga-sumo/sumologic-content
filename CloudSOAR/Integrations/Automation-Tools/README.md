# Automation Tools

## Whats included:
1. Integration YAML File
2. Action YAML Files (Refer to "Action Descriptions" section below for details)

## Disclaimer
This integration is in active development. Actions, or the parameters defined therin may change in subsequent releases.

## To use the content:
- Download the Integration and Action YAML files to your local device.
- Create a new CloudSOAR integration by logging into CloudSOAR > going to Settings (⚙)(top right) > Automation > Integrations > Plus(+) icon > and selecting the Integration YAML file.
- Add any Actions you downloaded to that Integration by selecting the Upload icon (hover over the newly added integration), and uploading the Action YAML file(s).
- For more information on uploading custom Integrations/Actions and how to test them, please see [Working with integrations](https://help-opensource.sumologic.com/docs/cloud-soar/cloud-soar-integration-framework/#working-with-integrations).

## Action Descriptions
### Data Transform
- Provides various functions to more easily transform data in a playbook:
  - **String Input** - The value to transform.
  - **Transform Function** - Which string operation to use. Valid options are 'Split', 'Strip', 'Replace' or 'Regex'
      - **Split**: Splits a string into an array based on the delimiter provided in the "Transform Argument" parameter.
      - **Strip**: Removes leading and trailing characters from a string. Space is the default character to remove, unless specified otherwise in the "Transform Argument" parameter.
      - **Append**: Attaches a string to the end of a string (String Input > Transform Argument)
      - **Prepend**: Attaches a string to the beginning of a string (Transform Argument > String Input)
      - **Replace**: Replace a specified string/word/character with the value specified in the "Transform Argument" parameter.
      - **Regex**: Match a string with a regex pattern (python regex). Currently, this will return only the first capture group/match in an array. Could be further modified to accept an array num input.
  - **Transform Argument** - Function input (e.g. regex pattern (w/ capture groups), replace argument (a,b) or split delimiter).
  - **Array Element** - Optional: if using 'split' function, select the element to return. Otherwise return the entire array.
  
### Filter IP Addresses
- Check a single IP, or list of IPs, and return a filtered list of IPs (sort into public IP and private IP lists).

### Generate Password
- Generates a random password. Length and character makeup are configurable.

### Get Time
- Fetches the current time
  - Optionally returns the time elapsed from "now" when provided a timestamp to compare the current time with.

### Check Time Boundaries
- Evaluates whether the current time is within business hours. Configurable start and end times. 24-hour format.

### Build JSON Object
- Provide the action with JSON key placeholder or string to build a new JSON object with the specified key/values.

### Buffer
- Takes a JSON string, or object and returns it as a JSON result. Helpful for dumping a JSON blob in string format and rendering in JSON format.

### Sleep
- Adds a configurable wait time to the execution of a playbook. 

### Get Time
- Returns the current time and provides an option to compare this time to a user-provided timestamp, returning elapsed time.

### Extract Domain from URL
- Extract the root domain from a URL

### Extract Domain from Email Address
- Extract the root domain from an email address

### Add External Alert to Incident
- Takes a JSON payload and attaches to a Cloud SOAR incident's "External Alert" section.

### Get External Alert
- Fetches the external alert(s) attached to an incident

  - _Note: You will need to specify yaml output mappings for each external alert you wish to fetch in order for this action to be usable within a playbook._

### Add Entity Metadata
- Searches for the specified entity object (IP, URL, etc.), locates the entity's ID first, and then adds a tag and/or description to this entity.

### Render TextArea Field
- Uses a _textarea_ field to build a string using dynamic placeholders.

### Get War Room Timeline
- Grabs the Incident's audit timeline and returns it in JSON format. This is useful for posting to a CIP HTTP source (using 'Generic HTTP POST' action)

### Generic HTTP POST
- Make a generic POST request.
- Usage:
  - **API URL** - The HTTP Endpoint to make the request to.
  - **Request Body as JSON** - a _textarea_ field to build a JSON result using placeholders.
  - **Request Body (output.raw JSON)** - accepts the raw JSON result from the output of a previous action.

### Get Incident
- Fetches Incident data (all fields, related incident IDs, as well as external alert data) and returns it in JSON format. This is useful for posting to a CIP HTTP source (using 'Generic HTTP POST' action)


### To upload your own content:
Please see [Sumo Logic Community Ecosystem Apps FAQs](https://help.sumologic.com/docs/integrations/community-ecosystem-apps/#faq).

### To add review/comment to content:
Please provide a review/comment for this content by following the guidelines below:

- Select the **Comments** folder.
- Open the **Comments.json** file.
- Select Edit (pen icon).
- Add a new line below the current comments, and paste in your review/comment using the following schema:

        {
            "reviewer":"[githubid/name]",
            "ratings":{
                "overall":4,
                "use-case":5,
                "design":4,
                "technical":4
            },
            "review":"This app is very useful for knowing x, y, and z. It would be great if the dashboards were broken out by use case instead of being one big dashboard."
        }


- Select **Propose New Changes**.
- Submit **Pull Request**.

Code owners will review and merge your comments on the content to the repo.

Please see [How to add a review/comment to an app](https://help.sumologic.com/docs/integrations/community-ecosystem-apps/#how-do-i-add-a-reviewrating-to-an-app) for more information.

### To upload your own content:
Please see [Sumo Logic Community Ecosystem Apps FAQs](https://help.sumologic.com/docs/integrations/community-ecosystem-apps/#faq).

### To add review/comment to content:
Please provide a review/comment for this content by following the guidelines below:

- Select the **Comments** folder.
- Open the **Comments.json** file.
- Select Edit (pen icon).
- Add a new line below the current comments, and paste in your review/comment using the following schema:

        {
            "reviewer":"[githubid/name]",
            "ratings":{
                "overall":4,
                "use-case":5,
                "design":4,
                "technical":4
            },
            "review":"This app is very useful for knowing x, y, and z. It would be great if the dashboards were broken out by use case instead of being one big dashboard."
        }


- Select **Propose New Changes**.
- Submit **Pull Request**.

Code owners will review and merge your comments on the content to the repo.

Please see [How to add a review/comment to an app](https://help.sumologic.com/docs/integrations/community-ecosystem-apps/#how-do-i-add-a-reviewrating-to-an-app) for more information.