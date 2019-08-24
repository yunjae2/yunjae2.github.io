---
layout: page
title: "dpt-manager: Document manager for Sony digital paper in Linux"
start_date: 2019-05-19
end_date: 2019-08-25
---

Linux users struggle to manage their Sony digital papers, because the official digital paper app supports only Windows and Mac.
There is [a project](https://github.com/janten/dpt-rp1-py) which provides a script to manage digital paper in Linux, which is developed by users.
However, the script is not that friendly to users.
If a user wants to upload or download a bunch of documents, she needs to run the script for every document.

Project dpt-manager was started because of this reason.
It provides some scripts to help users manage their documents.
Users can upload or download documents with just one command.
Also documents can be saved in online storage (git remote repository at this moment) and synchronized with the online storage.

This project is ended as [the project](https://github.com/janten/dpt-rp1-py) started to support sync operation.
I'm going to focus on implementing sync operation in the project.
