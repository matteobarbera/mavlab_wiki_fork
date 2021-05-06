## Data Storage:

1) **Project Data storage (staff-umbrella)**: this is a TU Delft network drive suitable for research data. To ask for this storage space, you have to go to **tudelft.topdesk.net > Software & Autorisations > IT for Researchers > Data Storage for Research > Aanvraag Data Opslag**. Please remember to ask only for standard availability. In the form you can specify the name of the storage space, and who you want to give access to (**internal or external to TU Delft**). The space will be created in **staff-umbrella** (in Windows systems it appears inside **Project Data (U:) **drive). If you are connected to the TU Delft network via eduVPN, the drive will be automatically mounted on your local system. If not, you can mount the drive locally in your device by using **Webdrive** (which is already installed in your Windows TU Delft laptop; FYI you can also download it from software.tudelft.nl). If you want to access the drives via the command line, then you can type: `sftp <your_net_id@sftp.tudelft.nl>` to connect with your netID. 
If you want to provide access to someone at a later stage, you can always do it by sending an email to <Servicepunt-LR@tudelft.nl>. Each space within staff-umbrella can be expanded up to **5TB** and they are managed by TU Delft ICT (which means automatic daily backups in TU Delft servers, and secured by institutional protocols and security services). For storage spaces larger than 5TB, the request goes via the Faculty ICT Manager Marco Bolleboom (<https://www.tudelft.nl/staff/m.e.bolleboom/> ). Keep in mind all spaces start at 50 GB and they get expanded as you used them. This means the size of the drive you specify in the form is only used as a reference.

2) **SURFdrive:** for easy data transfer and temporary data storage, you have a SURFdrive account (**<https://www.surfdrive.nl/> > Log In op Surfdrive > login with your NetID**). This is a **500 GB** storage space for your own personal use. We say it is temporary because it is linked to your contract to TU Delft (the space is shut once the TU Delft researcher leaves the TU Delft). It is **recommended for sensitive data**. Via SURFdrive you can share folders/files with other Surfdrive users (other staff members of Dutch universities). With external people (e.g., company collaborators) you can **share via link**. You can also **synchronize SURFdrive** with local directories using the desktop client <https://www.surf.nl/en/store-and-share-your-files-securely-in-the-cloud-with-surfdrive/downloads-for-surfdrive> Every research staff has a SURFdrive account (i.e., it includes PhDs, but not MSc students).

3) **Onedrive:** Each TU Delft employee has **1TB** of space via Onedrive. However, keep in mind Onedrive is **NOT meant for sensitive data**, but for standard data only (e.g., data that if there is a data breach, there are no legal consequences about it).
You can sign in here: <https://onedrive.live.com/about/en-us/signin/>
For sign in, use your NetID: **<yourNetID@tudelft.nl>**

Manuals can be found here: <https://www.tudelft.nl/en/it-manuals/office-365/>
Students have access to Onedrive with their NetID in contrast to SURFdrive (which is only available for employees).

4) **G Suite for TU Delft Students and Employees**. TU Delft has a Google workspace now where you can use various Google apps, such as Google Docs, Google Sheets, Google slides, etc. Keep in mind:

-   Sharing documents with people external to TU Delft is possible.
-   You don't have to pay if you exceed 15 GB of storage.
-   You can transfer created Google documents from your personal account to the TU Delft account.
-   It is **not meant for sensitive information/data** since everything you put in there is **not stored at TU Delft servers**. If you work with sensitive information/data, stick to services like SURFdrive, SURFfilesender and Project Storage (staff-umbrella).

**How to access it?**

- Go to Google Drive: [https://drive.google.com](https://drive.google.com/)

- Use the button "Go to Google Drive".

- At "Email or phone" enter your own NetID name with @g-tudelft.nl behind it ([**your_netid@g-tudelft.nl**](mailto:your_netid@g-tudelft.nl)). You are now in the normal login screen of TU Delft where you can log in with your netID and password.

- Verify it's you. Click on the button "Continue". You are now signed in to Google Drive. By clicking on the "+ New" button you can create various Google documents.

- If you have created a Google document, you can share it with students and colleagues within TU Delft or with people outside TU Delft by clicking the "Share" button. At "Enter names or email addresses", enter the name of a student or employee and a drop-down list with persons within TU Delft will appear. If you want to share the Google document with someone from outside TU Delft, just enter his/her email address. You must be sure that the email address is linked to Google. By clicking on the pencil you will see a list of rights that you can give the person on your Google document.

 ______________________________________________________

## Data transfer:

5) **SURFfilesender:** TU Delft researchers (including students) are also able to use SURFfilesender (<https://www.surffilesender.nl/en/about-surffilesender> ) for data transfer of files up to** 1 TB**, and **2 GB using end-to-end encryption**. You can access SURFfilesender with your NetID logging in <https://www.surffilesender.nl/en> This is **recommended for sensitive data** (especially for data exchange with MSc students). Senders have to be from TU Delft, but receivers can be internal or external to TU Delft.

 ______________________________________________________

**Version Control:**

6)** Gitlab:** TU Delft has a Gitlab instance for **version control**. Gitlab is the user interface for Git repositories and version control software. Meaning that if you are writing scripts for your research project and you struggle with version control or you have to write code in collaboration with other colleagues/students, then Gitlab is a nice tool to try. All TU Delft research staff (including PhD candidates) can login with their NetIDs and create a project. Students can login and can be invited to participate in projects, but cannot create projects on their own.\
Easy login once your project is created is done via <https://gitlab.tudelft.nl/users/sign_in>\
Some remarks:\
- Having a TU Delft instance means that everything you put in Gitlab will be kept within the** TU Delft network** (maintained by TU Delft ICT and stored in TU Delft Data Centers). Thus it is **recommended for the development of competitive/sensitive code**.\
- Please use Gitlab as a code repository and **not as personal storage**. Thus please remember to do git ignore on data files when pushing the changes to the code on the TU Delft Gitlab.

- Recommended for also keeping track of the code development within your group.

*To create a group:*

*--> go to **gitlab.tudelft.nl** and sign in with your NetID*

*--> go to **Groups** at the top left corner*

*--> create **New Group** (at the top right side, in a green box)*

*--> set up a name for the group*

*--> in **Your Groups** (**Groups** at the top left corner > **Your Groups**), select the group*

*--> in the left hand panel, go to **Members**. And then invite members to the group*

- Access to external users (meaning outside TU Delft) is possible but must be requested via the **tudelft.topdesk.net > Software & Autorizations > IT for Researchers > Gitlab TU Delft > Aanvraag externe toegang TU Delft**

7) **SVN:** TU Delft also has Subversion. Information about it can be found in **tudelft.topdesk.net > Software & Autorizations > IT for Researchers > Version control tools**.

 ______________________________________________________

## Training opportunities:

8) **Software Carpentry Workshop:** this is a two days workshop (4 half days in online mode) where we give an **introduction** about Bash, Python and Git. If you have a student or PhD who might need it or you are curious about it, you can check out the material we use here: <https://software-carpentry.org/lessons/> PhDs get credits from the Graduate School. Dates for the upcoming ones at TU Delft can be found via the following website: <https://www.tudelft.nl/en/library/current-topics/research-data-management/r/training-events/training-for-researchers/>

9) **Code Refinery Workshop:** this is a three days workshop (6 half days in online mode) about **version control and reusable code**. It is meant for all researchers, and when given by TU Delft, PhDs get credits from the Graduate School for it. You can take a look at the different possible lessons here <https://coderefinery.org/lessons/> also free to use. Dates can also be found via the following website: <https://www.tudelft.nl/en/library/current-topics/research-data-management/r/training-events/training-for-researchers/>

10)** eScience Center training**: the eScience center runs training for researchers, which include the previously mentioned Software Carpentry and Code Refinery workshops. Keep in mind that when eScience Center hosts the Software Carpentry and Code Refinery workshops, we cannot guarantee the PhDs will get Graduate School credits for participating in them. Check training opportunities or events via <https://www.esciencecenter.nl/events/>

 ______________________________________________________

## Open Access publishing:

11) **About (Green and Gold) Open Access publishing:**
**Open Access Publishing** refers to make the **research journal articles** freely available for everyone to read and hopefully build upon.\
There are essentially **2 types of journals** when it comes to Open Access:

**A) Journals that are 'full open access journals' (Gold Open Access journals).**
- This means that **readers do not have to pay** a subscription to the journal to see and download the articles.
- A list of full open access journals can be found in the DOAJ (<https://doaj.org/> ). In that website make sure you tick only the 'journals' and not the 'articles' (below the search tab). There you can see the journals and the **APC (article processing charge)** that must be paid to publish in that journal.
- Sometimes the university has some deals with these publishers (to have an APC discount). You can see whether there is an APC discount for a specific journal in the journal browser <https://library.wur.nl/WebQuery/tudbrowser?q=*> Sometimes the discount is of 20%, sometimes 100%! It depends on the publisher and the journal. 

If there is no 100% discount, then to pay for the APC, in principle the **budget should come from the project** (it should be included at the proposal stage). If there is no money in the project, then you can apply to the **TU Delft Open Access Fund** (see <https://www.tudelft.nl/en/library/library-for-researchers/library-for-researchers/publishing-outreach/open-access-funding>). However keep in mind this is given on a first-served basis and it is a fixed budget available for all TU Delft researchers of 50k euros a year (approx).
If there is no funding in the project nor the Open Access Fund, then you can ask within your department if there is budget for publishing.
If there is no funding to pay the APC, then you have to do what is called **Green Open Access** (see further below).

**B) Journals that are subscription-based journals (hybrid Open Access model).**
- This means that **readers have to pay a subscription** to be able to read the articles published in that journal.  This subscription is usually already covered by the TU Delft Library, so that TU Delft researchers can have access to those articles and also get to publish in those journals (with the articles being accessible only to subscribers).
- Some subscription-based journals give the possibility to publish in Open Access. Then there are two fees to pay: one fee to publish in that article (usually covered by institutions) and an **extra fee to publish the article in Open Access** (this fee it is** also called APC**; these APCs are usually more expensive than the ones paid for full open access journals).
- TU Delft sometimes has extra deals with publishers, so that TU Delft can get a discount when paying the APC. You can see whether there is an APC discount for a specific journal in the journal browser <https://library.wur.nl/WebQuery/tudbrowser?q=*> Sometimes the discount is of 20%, sometimes 100%! It depends on the publisher and the journal.
- To pay for that APC, the money should come from the **project or the department**.
- If there is no money to pay for the APC, then you have to publish in what is called **Green Open Access** (see below).

**What is green open access?**

Green open access refers to making a version of the article Open Access.

There are essentially three main versions of a journal article:
i) **Preprint**. This is the first draft the researcher sends to the publisher (so before the peer review).
ii) **Postprint or 'accepted manuscript'**. This is the accepted version (after the peer review). But **without all the layout of the publisher, and without the copyright statement** that the copyright belongs to the publisher.
iii) **Publisher's version**. This is the finalized document, with the layout of the publisher and the copyright statement that the copyright belongs to the publisher.

Since you are a TU Delft researcher, if you choose 'green open access' then you have to make sure that the journal allows you to make the **postprint open access in an institutional repository** (see below). You can always drop me an email to ask me about this information.

**Note that:**

- TU Delft open access publishing policy** (<https://www.tudelft.nl/en/library/library-for-researchers/library-for-researchers/publishing-outreach/creating-your-publishing-strategy/open-access-publishing>) states all **postprints should be made open access via the TU Delft Research repository** <https://repository.tudelft.nl/islandora/search/?collection=research>
- You can always **send me a list of the journals** you would like to publish in, and I can forward you the information about the **Article Processing Charge (APC)** to pay for Open Access (you retain the copyright and the article is immediately publicly available for everyone to download/read/etc.), or the **embargo period** under which the postprint has to remain closed (for Green Open Access).
- Whenever you publish an article, please **send the DOI** (persistent identifier) **of the finalized article** (publisher's version) **and the postprint **(without the layout and copyright stamp of the publisher) **to <PURE-LR-lib@tudelft.nl>**. Then staff from the library will make the postprint public (after the embargo period) via the TU Delft Research Repository ( <https://repository.tudelft.nl/islandora/search/?collection=research> ).

Plan S. Keep in mind Plan S is **finally starting** this year. The TU Delft has created a new [website](https://www.tudelft.nl/en/library/library-for-researchers/library-for-researchers/publishing-outreach/plan-s/) for it. What does Plan S mean in practical terms? For publications resulting from **NWO funding** calls opened from **1 January 2021** onwards, they must be available in open access immediately (**without embargo periods**) and with an **open license** (CC BY; more restrictive licenses can apply as exceptions). Publications in hybrid venues will be allowed only if the journal is a so-called Transformative Journal. Here is where the [list](https://www.coalition-s.org/plan-s-compliant-transformative-journals/) of Transformative Journals can be checked out. You can also check the [Journal Checker tool](https://journalcheckertool.org/) to see if a journal complies with Plan S.

Horizon Europe. Also keep in mind the new framework **Horizon Europe** is here! What does that mean in terms of publication of articles and data? 

Regarding **publication of articles**, the publication policy of Horizon Europe (HE) is aligned with what Plan S stands for. More specifically, for publications resulting from **HE funding** calls opened from **April 2021** onwards, they must be available in open access immediately (**without embargo periods**) and with an **open license** (CC BY or CC BY NC / ND / NC-ND). Publication in closed or hybrid journal will not be banned, but those fees will not be eligible for reimbursement.

Regarding **data**, what used to be **H2020 Open Research Data Pilot** will be the **norm in HE**. This means:

-   **share data** *as open as possible and as closed as necessary*;
-   each project should have a **Data Management Plan**;
-   **costs for RDM** (data storage, processing and preservation/archiving) will be eligible for all projects.

The main difference with respect to the **H2020 Open Research Data Pilot** is that for some actions of HE there will be the obligation to deposit the data in a repository that is **federated under the European Open Science Cloud** [**EOSC**](https://eosc-portal.eu/) (FYI: the [4TU.ResearchData](https://data.4tu.nl/info/en/) is not federated under the EOSC). Which actions? That remains to be defined.

See more information on HE [here](https://ec.europa.eu/research/participants/docs/h2020-funding-guide/other/event201009.htm).

 ______________________________________________________

**Online Repositories for data long-term archiving (what happens with the data/code 5, 10 years from now?):**

12) **DataverseNL:** This is an **online repository and archive managed by DANS** (Dutch Archiving and Networking Services in Den Haag). It is recommended for **all types of data** (not necessarily related to a journal article). If you go to **<https://dataverse.nl> > 4TU.ResearchData dataverse > Delft University of Technology** (<https://dataverse.nl/dataverse/delft> ) you can see the public repositories that are available from TU Delft researchers/research-groups. Dataverse also allows private repositories, where the admin (e.g., the TU Delft researcher) can give access to whoever they want/need to. In public dataverses you can also find files whose download is restricted. See an example here: <https://hdl.handle.net/10411/3F1F8T>

Public datasets within Dataverse are given **persistent identifiers** (a Handle or DOI). In principle it is meant for **fair-use**, so there are no explicit upper quotas for its use in terms of storage. However uploading TBs of data would rise an alarm. Thus, we suggest TU Delft researchers to upload **small-to-medium sized datasets** to the platform (meaning order of hundreds GBs tops). If you are interested in this platform, let me know (someone from Research Data services has to grant you admin rights).

13)** 4TU.ResearchData:** This is an **online repository and archive managed by the 4TU **(the federation of 4 tech universities of the Netherlands, which TU Delft is part of). It is recommended for publishing the data **underlying the results of published articles**. TU Delft researchers can upload up to **1TB of data per year free of charge**. It offers **public and private repositories**. At the 4TU.ResearchData private repositories are repositories where the description of the repository is public, but files are under permanent embargo.

A a new feature of this archive, is that it also allows **integration with Github**. This means that the 4TU.ResearchData archives a snapshot of a Github repo (where the code is publicly available), making this snapshot findable and accessible in the long-term (also providing the code a persistent identifier -a DOI- making it citable). By September 2021 there will be also an integration with Gitlab.

14) **Zenodo:** Zenodo is an **online repository and archive managed by CERN** (Switzerland). This repository provides public and private repositories for free, but **uploads can be of 50 GB max**. For uploads larger than that, Zenodo will/might ask for a "donation". Zenodo also provides the **integration with GitHub** (Zenodo makes a snapshot of a GitHub repository and archive that for the long-term, also providing the code a persistent identifier making the code citable). The main difference with the 4TU.ResearchData is that Zenodo (as Dataverse.nl) is **for all type of data** (not necessarily related to a journal article). For more information, check the following link: <https://guides.github.com/activities/citable-code/>

 ______________________________________________________

**Others:**

15)** ORCID:** Please make sure your **ORCID is linked to PURE**:
-login to your PURE profile using your NetID (<https://pure.tudelft.nl/admin/workspace.xhtml> )
-**edit profile**
-**add your ORCID**
Please also check whether your Scopus id is connected to your ORCID. PURE is the platform that collects all TU Delft research output and activities. But your **ORCID and Scopus are independent of the institution **you work in. To connect your Scopus id to your ORCID, go to your Scopus profile, and check the right hand side of the webpage (under **Profile actions**).
If you do not have an ORCID, it would be advisable to acquire one. You can do so by registering in <https://orcid.org/register> Whenever you publish either data/code or an article, you can add your ORCID in the author information and then all your research outcomes (independent of the institution) will show up in your ORCID account (so it is good for visibility).

16) **Standard Letter of Unpublished Work**: In the following link you can find the letter the Library prepared for whenever publishers "see" (MSc students) dissertations as "not original work":  <https://www.tudelft.nl/en/library/library-for-researchers/library-for-researchers/publishing-outreach/creating-your-publishing-strategy/standard-letter-on-unpublished-work>
You can send that letter to the publisher in case you encounter such a problem.
17) **Report!** We encourage researchers to **keep all communications within TU Delft email addresses**, especially when there is **exchange of sensitive information** among collaborators. However, there are **spam/phishing emails** that you will receive despite all efforts. These are emails that are not filtered by the security system that IT uses. Please be aware of these suspicious emails. If you **receive one or are not sure** if it is a bad email, just forward the email (or a text copy of it) to **<abuse@tudelft.nl>**. This will also help IT see why the suspicious email was not filtered but the security system.

18) As mentioned in our meeting: whenever you write a proposal, please contact the **contract manager** of the faculty via **<PST-AE@tudelft.nl>**. The contract manager is the person who checks the budget of the proposal. At a proposal stage you can also send me a list of the journals you aim to publish in and I can provide you the Open Access options (so that you consider it in the budget).

19) In case you have not heard of it, I would like to point you to [https://www.researchprofessional.com](https://www.researchprofessional.com/)

There you can do a first login with your TU Delft NetID, and you can find a lot of information about funding opportunities (European and national), awards and conferences.

20) **Surfsara:**  regarding Surfsara** supercomuting** facilities, here you can find information about how to apply in case you are interested: <https://www.nwo.nl/en/news/call-computing-time-national-computer-facilities-2021-open-submission>

21) Last but not least, I am hereby sending you the 'decision tree' that provides **contact info about the Business Connect Team and Valorisation Center**. It has a lot of information but it overall shows when to contact what at TU Delft. One comment: Rene Deijk is no longer working at our faculty. But aside that, everything else still applies.