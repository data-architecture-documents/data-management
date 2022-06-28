# Data management template (DMT)

This document is a checklist to find out how your data are managed. Just make a copy of this template and complete one for each set of dataset in your organisation. Once completed, you can place the resulting documents in a document store of your choice. One option is to construct a hierarchy of folders for your organisation in a github repository.

In this document we talk about datasets. As mentioned above, the idea is to create a copy of this document for each dataset you have. A database you have will typically contain one dataset so you can just create one of these documents for the database. However, a data warehouse may contain more than one dataset so you can create one document per dataset. For a data pipeline, in which you may be transforming data into a staging dataset en route to a final dataset, you can create a copy of this document for the staging dataset and one for the final dataset, so you can track how your staging data, as well as your final production dataset, are being managed.


## What

- Please give a one or two sentence succinct summary of your data, including the type of data. The description should be understandable by anyone.
- Is this production data, archived data or staging/temporary data? Please note this here.


## Where

- What is the physical location where the data are stored?
- What hosting company is used to store the data?
- What storage technology is used to store the data (e.g. Postgres)?
    - If in a data lake/warehouse or other shared database (e.g. GCP BigQuery) then include the names of the table(s) used to store your data.


## Context

This can include any of the following:

- Where does this dataset fit in the data lifecycle?
- How does it relate to other datasets covered by other DMTs? Include links to other DMTs here.
- What local applications use this dataset and how?


## Responsible person

- Which person is responsible for your data or the database/system that stores the data? This may be a technical or a commercial person, e.g. the technical lead.


## Source(s) of data

- Where do the data come from? For example the data may be publically available, customer data, data from elsewhere in GDS, or be a combination of any of these sources.
- If possible, include links to DMTs for data sources, if there are any.


## Consumer(s)

- Who uses/consumes the data? Here you can list all the downstream IT systems or groups of users.
- If possible, include links to DMTs for downstream data sources, if there are any.
- Is there anyone else who is interested in the data you have, and who can be alerted in case there are ever any issues with the data?


## Access permissions

### Write permissions

- Which roles, or which users, have permissions to update/modify/delete the data? This could be both technical and non-technical people.

### Read permissions

- Which roles, or which users, can view the data? This could be both technical and non-technical people.


## How much data is being stored

Please fill in one of the following sections, depending on the type of data you have (production, archived, staging/temporary data):

- For production data:

    - How much data are immediately available to your consumers? For example, you may only have the past 6 months worth of data immediately queryable. If you don't have archiving/deletion of data once the data are no longer required then just answer "All".

- For archived data:

    - How much data are stored in an archive? For example, you may archive any data over 6 months old.
    - If you have archived data:
        - Briefly, what is the process for recovering data from an archive so it can be made available to systems/people consuming the data?
        - Is the recovery process tested to verify it works and the recovered data tested to verify the recovered data are intact?
        - Are there any service level agreements (SLA) outlining how long it takes to make data available to consumers/users? You could briefly list any SLA here.

- For staging/temporary data:

    - This refers to data that are stored en-route to arriving at your final set of production data? For example, you may have staging data saved during a data pipeline.
    - Note how long you are retaining these data for.


## Current?

- Is this data source still being populated? If it's no longer being populated then include the last date data were added to the data source.


## Privacy

- Do you store any confidential data or personally-identifiable information (PII)? If so, then give some brief details.
- If you have removed PII then please also note this fact here.


## Auditing

- Do you have any audit information for your data? This may include where the data came from, who/what has modified the data.
    - If so, is the audit information stored per record (i.e. for each row of data in your database tables) or per batch (i.e. for a set of data that have been loaded into your database)?
