# Data management

This page provides guidelines on the management of data. To be clear: 'data' implies both 'data' and 'code'. New PhDs are required to set up a data management plan (DMP), which can be done using the [DMPonline](https://dmponline.tudelft.nl/) tool provided by TU Delft. Below you can find guidelines on parts of the DMP:

- Data storing/sharing platforms
- Software-specific licences
- Data-specific licences
- Metadata standards

Each section contains an overview of available options, and also recommendations based on what is being used/preferred at the MAVLab. Further questions regarding management of data and code can be directed to the faculty data steward, Dr. Heather Andrews (find her email in the TU Delft webmail address book).

## Data storing/sharing platforms

There are many options when it comes to storing and sharing data. Here, we distinguish between general data storage and sharing, code repositories, and data repositories.

### General data storage/sharing

|                     | Type  | Space                            | Sharing options                  | Sensitive data? | Purpose                                                                 |
|---------------------|-------|----------------------------------|----------------------------------|-----------------|-------------------------------------------------------------------------|
| TUD network drive   | SFTP  | < 5 TB                           | Ask IT; only whole-drive sharing | Yes             | Storing large amounts of long-term project data for an entire team      |
| SURFdrive           | Cloud | 500 GB                           | Via email address or link        | Yes             | Storing relatively large amounts of data while maintaining quick access |
| SURFfilesender      | Cloud | 1-2 TB (depending on encryption) | Via email address or link        | Yes             | Sending files securely                                                  |
| OneDrive/Sharepoint | Cloud | 1 TB                             | Via email address or link        | No              | ?                                                                       |

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