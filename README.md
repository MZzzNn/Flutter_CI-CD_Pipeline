# CI/CD Build APK and Upload to Drive and Send Link to Telegram Channel and Send to Gmail Account

This repository provides a streamlined CI/CD workflow for building Flutter APKs, uploading them to Google Drive, sending the download link to a Telegram channel, and sending a notification email to a Gmail account. It automates the tedious tasks involved in the build and distribution process, saving you time and effort.

## Workflow Overview

The workflow defined in this repository performs the following steps:

1. On every push to the `master` or `test` branch, the workflow is triggered.
2. The workflow checks out the repository and retrieves relevant information such as the branch name, project name, commit author, commit author email, and commit author date.
3. The Flutter environment is set up, including Java and Flutter versions.
4. The build process begins by cleaning the build folder and fetching package dependencies.
5. The script builds the APK in release mode without tree-shaking the icons.
6. The workflow obtains the appropriate Google Drive folder ID based on the branch name.
7. The files are archived and uploaded to Google Drive, specifying the folder ID and a unique name based on the branch and timestamp.
8. A notification is sent to the specified Telegram channel, providing details about the build and a link to download the APK from Google Drive.
9. An email notification is sent to the specified Gmail account, including the project, branch, and date details, along with the Google Drive download link.

## Usage

To use this CI/CD workflow for your Flutter project, follow these steps:

1. Fork this repository or create a new repository based on this template.
2. Configure the necessary secrets in your repository settings:
    - `MASTER_FOLDER_ID`: Google Drive folder ID for the `master` branch.
    - `TEST_FOLDER_ID`: Google Drive folder ID for the `test` branch.
    - `GOOGLE_DRIVE_CREDENTIALS`: Service account credentials JSON for Google Drive access.
    - `TELEGRAM_CHANNEL_ID`: Telegram channel ID for sending notifications [get it here](https://t.me/getidsbot).
    - `TELEGRAM_TO`: Comma-separated list of Telegram user IDs or usernames to send notifications to [get it here](https://t.me/username_to_id_bot).
    - `TELEGRAM_BOT_TOKEN`: Telegram bot token for sending notifications [get it here](https://t.me/botfather).
    - `GMAIL_USERNAME`: Gmail account username for sending notification emails.
    - `GMAIL_PASSWORD`: Gmail account password or an [app-specific password](https://support.google.com/accounts/answer/185833?hl=en) for sending notification emails.
3. Customize the email notification's content in the `Notify Gmail` step to match your requirements.
4. Commit and push your changes to trigger the CI/CD workflow.

That's it! Now, whenever there's a push to the `master` or `test` branch, the workflow will automatically build the APK, upload it to Google Drive, send the link to the Telegram channel, and send a notification email to the specified Gmail account.

Feel free to customize and enhance the workflow to suit your specific needs.

## Notes

- Ensure that you have the necessary permissions and access to the Google Drive folders, Telegram channel, and Gmail account.
- Make sure to keep your secrets secure and avoid exposing them in public repositories.

## Feedback

- If you have any questions or suggestions, don't hesitate to send me.

