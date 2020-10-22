# Miro Steps

These steps allow you to interact with Miro's online whiteboard.


---------

<kbd>
<a href="https://support.xmatters.com/hc/en-us/community/topics">
   <img src="https://github.com/xmatters/xMatters-Labs/raw/master/media/disclaimer.png">
</a>
</kbd>

---------

# Files

* [MiroOnlineWhiteboard.zip](MiroOnlineWhiteboard.zip) - Workflow zip file with the step and example flow
* [miro.png](/miro.png) - Miro logo

# How it works
These steps use the [Miro API](https://developers.miro.com/reference#introduction) to create boards and post to boards.


# Installation

## Miro Setup

You need a Miro account for this integration.

1. You'll need to generate an API token from your Miro account.
2. Follow the steps here (https://developers.miro.com/docs/getting-started) to get your Token. The permissions `boards:read` and `boards:write` should be suitable for the xMatters steps.
3. Copy the created token for use in the xMatters Steps.

## xMatters Setup
1. Download the [MiroOnlineWhiteboard.zip](MiroOnlineWhiteboard.zip) file onto your local computer
2. Navigate to the Workflows tab of your xMatters instance
3. Click Import, and select the zip file you just downloaded
4. Create an endpoint for Miro that uses Basic Authentication (username and password from Miro). The endpoint should have the base URL `https://api.miro.com`.
5. Create a constant for the token you copied during the Miro Setup.


## Usage
The steps are now available for use in a workflow.

### Miro - Create Board
---
### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| BoardName | No | 0 | 200 | Name of board to create. | | No |
| sharingPolicy-access | No | 0 | 200 | sharingPolicy.access can be private, view, comment | view | No |
| sharingPolicy-teamAccess | No | 0 | 2000 | sharingPolicy.teamAccess can be private, view, comment, edit | | No |
| token | No | 0 | 2000 | Grab your account API token | | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| response | Response message. |
| boardId | ID of the board created. |
| viewLink | Link to the board for viewing in browser. |


### Miro - Post to Board
---
### Inputs
| Name  | Required? | Min | Max | Help Text | Default Value | Multiline |
| ----- | ----------| --- | --- | --------- | ------------- | --------- |
| BoardId | No | 0 | 200 | ID of the board to add to. | | No |
| type | No | 0 | 200 | This endpoint currently supports next widget types: card, sticker, text, shape, line. | Sticker | No |
| text-title | No | 0 | 2000 | Title of the card (typically incident number) | | No |
| token | No | 0 | 2000 | Grab your account API token | | No |
| text-detail | No | 0 | 2000 | Detail message content | | No |


### Outputs

| Name | Description |
| ---- | ----------  |
| response | Response from Miro. |


## Example Flow
This is what the provided flow with the steps looks like.

<kbd>
	<img src="/media/ExampleFlow.png">
</kbd>

