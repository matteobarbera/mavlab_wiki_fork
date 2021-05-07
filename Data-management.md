# Data management

This page provides guidelines on the management of data that will inevitably accumulate during your work at the MAVLab. To be clear: 'data' implies both 'data' and 'code'. For new PhDs and certain grant applications, it has become mandatory to write a data management plan (DMP). This can be done easily using the [DMPonline](https://dmponline.tudelft.nl/) tool provided by TU Delft and the guidelines from this wiki page. Below, the most important aspects of data management that should concern everybody at the MAVLab will be covered.

- [General philosophy](#general-philosophy)
- [Data storing/sharing platforms](#data-storingsharing-platforms)
- [Licenses for software](#licenses-for-software)
- [Licenses for data](#licenses-for-data)
- [Documentation and metadata](#documentation-and-metadata)

Each section contains an overview of available options, and also recommendations based on what is being used/preferred at the MAVLab. Further questions regarding management of data and code can be directed to the faculty data steward, Dr. Heather Andrews (find her email in the TU Delft webmail address book). Also consider this overview provided by Heather: [[Information-from-data-steward]]

## General philosophy
Data that is generated as part of your research should be FAIR, that is Findable, Accessible, Interoperable and Reusable. This means that you should make sure, that at latest when publishing a paper on your generated data, you should also publish the data alongside it. This does not only help others to better understand your work, but also increases transparency. It also means that this data should be documented properly so that others (including yourself a year later) can understand how to use it.

At the MAVLab, our goal is to increase the impact of our data and code, which is why we don't want to restrict its use unnecessarily. Where possible, we therefore prefer licenses such as CC0 for data and MIT or BSD for software.

Finally, even though data management often only comes to mind before publishing something, proper documentation (especially for code) should be done continuously and proper use of data storage technologies is important at any step during a project. After all, you don't want to lose all of your research data if your laptop gets stolen...

## Data storing/sharing platforms

There are many options when it comes to storing and sharing data. Here, we distinguish between general data storage and sharing, code repositories, and data repositories.

### General data storage/sharing

|                     | Type  | Space                            | Sharing options                  | Sensitive data? | Purpose                                                                 |
|---------------------|-------|----------------------------------|----------------------------------|-----------------|-------------------------------------------------------------------------|
| TUD network drive   | SFTP  | < 5 TB                           | Ask IT; only whole-drive sharing | Yes             | Storing large amounts of long-term project data for an entire team      |
| SURFdrive           | Cloud | 500 GB                           | Via email address or link        | Yes             | Storing relatively large amounts of data while maintaining quick access |
| SURFfilesender      | Cloud | 1-2 TB (depending on encryption) | Via email address or link        | Yes             | Sending files securely                                                  |
| OneDrive/Sharepoint | Cloud | 1 TB                             | Within TU Delft via email address        | No              | ?                                                                       |

The above table lists some options for data storage and sharing. Note that anything involving TU Delft or SURF is usually fine for storing sensitive data, because these servers are hosted inside the Netherlands. While options like SURFfilesender have more polished and easier-to-use alternatives such as WeTransfer, the former should be preferred. 

The network drives are known to be slow because your computer doesn't actually keep local copies of every file on the drive. This might be preferred in cases when local disk space is in short supply, but as long as your storage demands don't exceed 500 GB, SURFdrive is often a better alternative. You can login with your NetID, files can be shared easily, and to have local copies you can connect it to any device you like using the [ownCloud client](https://owncloud.com/desktop-app/) (Windows, Mac, Linux, iOS, Android). Network drives can be requested via [TOPdesk](https://tudelft.topdesk.net).

### Code repositories

|                                        | TUD GitLab                                                  | GitHub                                                              |
|----------------------------------------|-------------------------------------------------------------|---------------------------------------------------------------------|
| Private repositories and collaborators | Unlimited                                                   | Unlimited (apply for PRO account using your student/employee email) |
| Hosting server                         | TU Delft                                                    | U.S.                                                                |
| Snapshot (for publishing)              | Via Zenodo                                                  | Via 4TU.ResearchData or Zenodo                                            |
| Accessibility                          | Only staff can create; external users should request access | Anyone can create; anyone can be invited                            |
| Visibility                             | Very limited                                                     | Maximized                                                           |

The main trade-off between GitLab and GitHub is one of security versus visibility. GitLab repositories are hosted on TU Delft's servers, which makes them suitable for sensitive data. However, TU Delft GitLab projects cannot be found through regular Google searches, meaning visibility is very limited. People outside of TU Delft need to apply for an account in order to access it. This means that GitLab is mainly useful as a repository for research that is in progress, with TU Delft collaborators only.

GitHub, on the other hand, maximizes visibility (when repositories are public). So when your project doesn't contain sensitive data, GitHub is the way to go. Be sure to apply for a free PRO account as a student or staff member [here](https://education.github.com/) (also comes with many other free things!).

### Data repositories

|             | Space                           | Max file size | GitHub snapshot? | Repo type        | Server location    | When to use?                           |
|-------------|---------------------------------|---------------|------------------|------------------|--------------------|----------------------------------------|
| 4TU.ResearchData  | 1 TB per year                   | 10 GB         | Yes              | Public           | Netherlands        | Published & long term preservation     |
| DataverseNL | 100 GB                          | 2 GB          | ?                | Public & private | Netherlands        | During research; sharing within MAVLab |
| Zenodo      | Unlimited but 50 GB per dataset | None          | Yes              | Public & private | Switzerland (CERN) | During research; sharing outside TUD   |

Data repositories can be used to make your dataset citeable (DOI) and easy to find. Given that TU Delft has good options here, the current recommendation is to use DataverseNL when research is in progress, and to move everything to 4TU.ResearchData when publishing. For DataVerseNL, there is a [MAVLab account](https://dataverse.nl/dataverse/mavlab) that can be used (futher information on DataverseNL [here](https://data.4tu.nl/info/en/use/manage-share)). You can log in with your NetID on 4TU.ResearchData [here](https://data.4tu.nl/info/en/).

## Licenses for software
Since we promote transparency on the methods used in our research according to our General Philosophy, publishing software is recommended wherever possible. Since this software will be made available on the public domain as an open-source project (if possible). This means that all this software should be properly licensed to prevent legal issues. If you are wondering if a license is necessary for your project, take a look at  [this](https://choosealicense.com/no-permission/) link. 

One of the most permissive licenses around (and one commonly used in the MAVLab) is the [MIT license](https://choosealicense.com/licenses/mit/#suggest-this-license). The only conditions are the preservation of copyright and license notices. Whenever possible, it is advised to use this license.

Another option is the [Apache License 2.0](https://choosealicense.com/licenses/apache-2.0/) which differs mainly in the fact that with this license, people should make proper documentation of the changes made to the source code. 

A more restrictive license is the [GNU GPLv3](https://choosealicense.com/licenses/gpl-3.0/), where the user cannot distribute the material without disclosing the source code (which is allowed in the previous two licenses).

An list of available licenses can be found [here](https://choosealicense.com/licenses/) or a really extensive list [here](https://spdx.org/licenses/)

If you are not sure what license to use, use the [license selector](https://ufal.github.io/public-license-selector/) or contact the Data Steward of AE (currently Heather Andrews Mancilla).

If you are using licensed code in your own repo, be sure to check what is permitted and what not. Always make sure to properly credit and mention the authors and licenses of the code used. A very nice tutorial on how to do this can be found [here](https://reuse.software/tutorial/)

## Licenses for data
The same philosophy applies to the data. If you are not sure about the license, you can check [TU Delft copyright information page](https://www.tudelft.nl/library/copyright) or [license selector](https://ufal.github.io/public-license-selector/). 

If the owner of the data is TUD, researchers have the right to choose the license. It also means that you have to evaluate how sensitive your data is (for example, if you have any personal information/commercial/confidential/etc.). The recommendation is to "open" your data as much as possible (CC0). 

## Documentation and metadata
It is always recommended to have a "good" readme file with your data and codes for you and others' sake.

You can consider including these things in your README file.
- Description of the data
- How you collected the data
- How to set up the software (requirement, installation, tested on what environment, etc.)
- How to use your data or code
- How to reproduce your examples
- How to cite your data
- Who is maintaining it

If you use a data repository service(for example Dataverse, 4TU Centre, Zenodo), they will ask you for necessary information when you upload your data. Also, Dataverse and Zenodo support exporting the Metadata in various formats.

## MAVLab data storage
Code
- MAVLab Github: [github.com/tudelft](github.com/tudelft)
- SVN: svn.lr.tudelft.nl

Public data
- DataverseNL: [https://dataverse.nl/dataverse/mavlab](https://dataverse.nl/dataverse/mavlab)
- 4TU.Centre: [https://data.4tu.nl/search?q=mavlab](https://data.4tu.nl/search?q=mavlab)
