# RPA UiPath
The goal of this project is to create a collection of mp3 files of songs from the "Liked Songs" playlist in the Spotify user account. The process has three distinguishable parts:
- scrap the playlist info (artist - title) from Spotify web app (https://open.spotify.com/)
- find song videos in the web
- convert video links to mp3 and download.
To run this project user needs to have installed UiPath Studio (https://download.uipath.com/beta/UiPathStudioSetup.exe) and Chrome with UiPath extension enabled (https://docs.uipath.com/studio/docs/extension-for-chrome). To have more control over the process, the option “Ask where to save each file before downloading” should be enabled in the Chrome settings (https://support.google.com/chrome/answer/95759?co=GENIE.Platform%3DDesktop&hl=en). 
Project doesn't use Orchestrator at any point, so basic knowledge of how to run Uipath projects is enough.
Login process doesn't include user credential retrieval - not from Windows Credential Manager, nor from Orchestrator assets or files. Instead, program stops for 10 sec to let user to login to Spotify.
To find the most relevant link for user's Artist - Title pair, program calculates similarity of user's query and search results and choses the one with highest similarity score.
To convert video link to mp3 program uses online service YouTube2Mp3 (https://ytmp3.cc). To prevent delays related to server response and internet speed this part of the program includes more strengthened retry mechanisms and error handling.
Errors also can happen due to the absence of appropriate video links in the web.
To track the workflow of the program and troubleshoot problems, a log file is prepared in Excel format, which contains information about errors and workflows that cause them.

