# Overview

Rightsline’s Avails endpoints enable developers to search for Avails Windows. The results mimic the Availability Report in Rightsline.

Within the Rightsline application, dimensions are indicated by system indicators at the database level to allow for clients to rename dimension fields to suit their needs. Because of this, dimensions 1 – 4 will be represented by their IDs for the requests and responses, while Term Start, Term End, and Exclusivity will have their own objects.

A new message will be available on Rightline SQS and SNS offerings with an action of availability-changed.

| ID | Name        | Type    |
| -- | ----------- | ------- |
| 1  | Media       | Array   |
| 2  | Territory   | Array   |
| 3  | Language    | Array   |
| 4  | Channel     | Array   |
| 5  | Term Start  | Date    |
| 6  | Term End    | Date    |
| 7  | Exclusivity | Boolean |
