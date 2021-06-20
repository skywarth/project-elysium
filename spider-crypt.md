# Spider Crypt

Includes several submodules which share one goal in common: autonomously crawl designated addresses.

## Submodules

- Sloth 
- Greed
- Gluttony  

---

## Sloth
Given a list of URL addresses, it will crawl the websites for sensible information. List of URL addresses are expected to be news websites. Therefore, it is crucial to prepare a DOM read algorithm that is fit for all. Could the old boy RSS be a good candidate ?

### Glossary

- S.H.I.T.E: Simply horrible and intolerable turd entry. 

- Crawls the URL addresses given by the user on a regular interval. By default, this interval is two times per day. For morning and evening news. 
- Filters any B.S.,Fake News, Based, X Pilled, according to the user.
- Stores fetched resources in local storage.
- Fetched resources will be bundled and prepared into a ready-to-consume state. Markdown (*.MD) will suffice for this purpose. Each of these will be called "report".
- User may mark certain news entries as "S.H.I.T.E". When marked, that entry will be deleted from the report file. With a simple Task/Schedule/Job, news entries marked as "S.H.I.T.E" will be run against a comparison function. 
- This comparison function may be using well-known data mining algorithms such as bayes, SVM, decision tree. *Actually it could be better to use clustering techniques here.* Another option is to build up a frequency, association and similarity database and compare it with that. All-in-all, model will be built using the marked entries. 
- Future reports will be cleansed from S.H.I.T.E content before serving to user.


### Components

- URL Targets List
  - Expected to be in conventional tabular data formats (CSV, XLS, JSON)
- S.H.I.T.E point calculator function
- A database for holding similarity data

- *Continue from here*
---


