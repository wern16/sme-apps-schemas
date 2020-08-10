# Schema Types

<details>
  <summary><strong>Table of Contents</strong></summary>

  * [Query](#query)
  * [Objects](#objects)
    * [GRPS_Comment](#grps_comment)
    * [GRPS_Company](#grps_company)
    * [GRPS_Company_Participant](#grps_company_participant)
    * [GRPS_ContentLink](#grps_contentlink)
    * [GRPS_Contribution](#grps_contribution)
    * [GRPS_CountryCd](#grps_countrycd)
    * [GRPS_DataSourceCd](#grps_datasourcecd)
    * [GRPS_Image](#grps_image)
    * [GRPS_LanguageCd](#grps_languagecd)
    * [GRPS_LocalString](#grps_localstring)
    * [GRPS_Local_Participant](#grps_local_participant)
    * [GRPS_Member](#grps_member)
    * [GRPS_Participant](#grps_participant)
    * [GRPS_ParticipantType](#grps_participanttype)
    * [GRPS_PartyName](#grps_partyname)
    * [GRPS_Product](#grps_product)
    * [GRPS_Product_Version](#grps_product_version)
    * [GRPS_Recording_Project](#grps_recording_project)
    * [GRPS_Repertoire_Owner](#grps_repertoire_owner)
    * [GRPS_Song](#grps_song)
    * [GRPS_Track](#grps_track)
    * [GRPS_User_Message](#grps_user_message)
    * [Participant](#participant)
  * [Enums](#enums)
    * [ContributorClass](#contributorclass)
    * [ImageUsageType](#imageusagetype)
    * [Source](#source)
  * [Scalars](#scalars)
    * [Boolean](#boolean)
    * [Date](#date)
    * [Datetime](#datetime)
    * [ID](#id)
    * [Int](#int)
    * [String](#string)
    * [URL](#url)
  * [Interfaces](#interfaces)
    * [GRPS_ContributorWork](#grps_contributorwork)

</details>

## Query
<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>findGRPSParticipantByName</strong></td>
<td valign="top">[<a href="#grps_participant">GRPS_Participant</a>!]</td>
<td>

Search across for GRPS specific Participants, and if referenced, delegate to RDX service to find external links
# Search for matching Participant from the GRPS backend service
# Return GRPS_Participant type for each matching GRPS Participant
# A reference to a extParticipants field causes the federation to delegate to RDX service using GRPS Participant id and source
# RDX service finds all external Participants (id and source) mapped to the GRPS Participant
# A reference to a Spotify Participant field on the external Participant causes the federation to delegate to SPOT_Participant field
# The result is a GRPS Participant with a collection of external linked Participants

</td>
</tr>
<tr>
<td colspan="2" align="right" valign="top">limit</td>
<td valign="top"><a href="#int">Int</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" align="right" valign="top">offset</td>
<td valign="top"><a href="#int">Int</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" align="right" valign="top">query</td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

## Objects

### GRPS_Comment

Defines a localized, ordered entity comment

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>text</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>updateDt</strong></td>
<td valign="top"><a href="#datetime">Datetime</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>updateBy</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Company

A Company associated with the Participant, Project, Product.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Company_Participant

Identifies the local Company Participant id and name

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>company</strong></td>
<td valign="top"><a href="#grps_company">GRPS_Company</a></td>
<td>

The associated Company

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>localId</strong></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The local Company Participant Identifer

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>localName</strong></td>
<td valign="top"><a href="#grps_partyname">GRPS_PartyName</a></td>
<td>

The local name of the Participant in the designated language

</td>
</tr>
</tbody>
</table>

### GRPS_ContentLink

Defines an content links for an entity

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>url</strong></td>
<td valign="top"><a href="#url">URL</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>text</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>desc</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a></td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Contribution

Defines a Participant Credit or Contribution to a Recording Project, Product Version, Product or Track

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>contributor</strong></td>
<td valign="top"><a href="#grps_participant">GRPS_Participant</a>!</td>
<td>

Idenifies the Participant Contributor

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>roleClass</strong></td>
<td valign="top"><a href="#contributorclass">ContributorClass</a>!</td>
<td>

Defines the high level role for the Particpant contribution

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>roleType</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

Defines the specific role the Participant contribution (e.g. DDEX Contributor Roles)

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>contributeToEntity</strong></td>
<td valign="top"><a href="#grps_contributorwork">GRPS_ContributorWork</a>!</td>
<td>

The entity for which the Participant contributed to its production

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>isConfidential</strong></td>
<td valign="top"><a href="#boolean">Boolean</a></td>
<td>

A flag to indicate the Participant's role in the work is confidential

</td>
</tr>
</tbody>
</table>

### GRPS_CountryCd

Identifies the valid country codes

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>code_2</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The ISO 3166-2 2 character alpha Country Code

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>code_3</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The ISO 3166-3 3 character alpha Country Code

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>name</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The country name

</td>
</tr>
</tbody>
</table>

### GRPS_DataSourceCd

Type type of group membership

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>code</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>title</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Image

Defines a internet accessible image for use with Entities

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>url</strong></td>
<td valign="top"><a href="#url">URL</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>text</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>height</strong></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>width</strong></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>usage</strong></td>
<td valign="top"><a href="#imageusagetype">ImageUsageType</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_LanguageCd

Identifies the language for localized values

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>script</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>language</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_LocalString

Localized text.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>text</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>language</strong></td>
<td valign="top"><a href="#grps_languagecd">GRPS_LanguageCd</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Local_Participant

Identifies the local Participant id and name

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>country</strong></td>
<td valign="top"><a href="#grps_countrycd">GRPS_CountryCd</a></td>
<td>

The local Country

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>localId</strong></td>
<td valign="top"><a href="#string">String</a></td>
<td>

The local Country Participant Identifer

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>localName</strong></td>
<td valign="top"><a href="#grps_partyname">GRPS_PartyName</a></td>
<td>

The local name of the Participant in the designated language

</td>
</tr>
</tbody>
</table>

### GRPS_Member

Defines a member in a group of participants.

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>memberType</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

Defines the type of membership for a participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>member</strong></td>
<td valign="top"><a href="#grps_participant">GRPS_Participant</a></td>
<td>

Member Participant

</td>
</tr>
</tbody>
</table>

### GRPS_Participant

Individual, Band Artists, Participants
@ToDo - Add Rep Owner, Participant Main Artist relations, and Participant Credits

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The source system, unique identifier for the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td>

A moniker identifying the source backend service for this instance of a Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>extParticipants</strong></td>
<td valign="top">[<a href="#participant">Participant</a>!]</td>
<td>

A collection of mapped, external (Spotify, Gracenote, Orchard, etc.) Participant Entities

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>name</strong></td>
<td valign="top"><a href="#grps_partyname">GRPS_PartyName</a>!</td>
<td>

The fully qualified, localized name for the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>disambiguation</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

Information to assist in identifying similar artist names (e.g. Characteristics)

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>nativeLanguage</strong></td>
<td valign="top"><a href="#grps_languagecd">GRPS_LanguageCd</a></td>
<td>

The native language of the participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>legalName</strong></td>
<td valign="top"><a href="#grps_partyname">GRPS_PartyName</a></td>
<td>

The legal name for the Participant, if different than the Participant name

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>isPreferred</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

Flag to assist in disambiguating possible duplicate Participants

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>localizedNames</strong></td>
<td valign="top">[<a href="#grps_partyname">GRPS_PartyName</a>!]</td>
<td>

A collection of localized names for the primary name of Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>altLocalParticipants</strong></td>
<td valign="top">[<a href="#grps_local_participant">GRPS_Local_Participant</a>!]</td>
<td>

A collection of local country information for the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>altCompanyParticipants</strong></td>
<td valign="top">[<a href="#grps_company_participant">GRPS_Company_Participant</a>!]</td>
<td>

A collection of Company specfic information for the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>altNames</strong></td>
<td valign="top">[<a href="#grps_partyname">GRPS_PartyName</a>!]</td>
<td>

A collection of also known as names for the Participant (e.g.
'Beyonce' is also known as 'Queen B', 'Bruce Springsteen' is
also known as 'The Boss').  This collection may include
the Legal Name for the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>participantType</strong></td>
<td valign="top"><a href="#grps_participanttype">GRPS_ParticipantType</a>!</td>
<td>

Defines the type of Paricipant (e.g. Person, Individual,
Band or Compound Artist). This is a key table for valid
Participant Types

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>repOwner</strong></td>
<td valign="top"><a href="#grps_repertoire_owner">GRPS_Repertoire_Owner</a></td>
<td>

The Repertoire Owner for the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>memberOf</strong></td>
<td valign="top">[<a href="#grps_member">GRPS_Member</a>!]</td>
<td>

Identifies Particpant membership in a group

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>members</strong></td>
<td valign="top">[<a href="#grps_member">GRPS_Member</a>!]</td>
<td>

Identifies member Participats of this Participant group

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>dateOfBirth</strong></td>
<td valign="top"><a href="#date">Date</a></td>
<td>

Date of Birth

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>dateOfDeath</strong></td>
<td valign="top"><a href="#date">Date</a></td>
<td>

Date of Death

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>nationality</strong></td>
<td valign="top"><a href="#grps_countrycd">GRPS_CountryCd</a></td>
<td>

The nationality of the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>cityAffliation</strong></td>
<td valign="top"><a href="#string">String</a></td>
<td>

City associated with Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>typicalRoles</strong></td>
<td valign="top"><a href="#string">String</a></td>
<td>

Most frequent contributor roles

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>contributions</strong></td>
<td valign="top">[<a href="#grps_contribution">GRPS_Contribution</a>!]</td>
<td>

Participant Contributions

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>comments</strong></td>
<td valign="top">[<a href="#grps_comment">GRPS_Comment</a>!]</td>
<td>

Notes and comments regarding Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>userMessages</strong></td>
<td valign="top">[<a href="#grps_user_message">GRPS_User_Message</a>!]</td>
<td>

User messages posted to the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>images</strong></td>
<td valign="top">[<a href="#grps_image">GRPS_Image</a>!]</td>
<td>

Participant images

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>relatedContent</strong></td>
<td valign="top">[<a href="#grps_contentlink">GRPS_ContentLink</a>!]</td>
<td>

Related Participant Content Links

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>whereUsed</strong></td>
<td valign="top">[<a href="#string">String</a>!]</td>
<td>

A collection of downstream systems dependent on this Participant

</td>
</tr>
</tbody>
</table>

### GRPS_ParticipantType

The Type of Artist with localized titles

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>title</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>eligibleMember</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>eligibleGroup</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>participantSubTypes</strong></td>
<td valign="top">[<a href="#grps_localstring">GRPS_LocalString</a>!]</td>
<td>

Defines a further classification of the type of Participant

</td>
</tr>
</tbody>
</table>

### GRPS_PartyName

A fully qualified, localized party name

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>fullName</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The complete name of the Party in its normal
form of presentation (e.g. John H. SMith, Acme
Music Inc., The Beatles)

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>asciiFullName</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The fullname transcribed into 7-bit ASCII characters

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>indexName</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The complete name of the Party in the form in which it
normally appears in an alphabetic index, with
the KeyName first (e.g. Smith, John H.; Beatles, The)

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>namesBeforeKeyName</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The names (aka First Name) preceeding the KeyName in the
full name (e.g. 'George' in 'George Michael'; 'John
Fitzgerald' in 'John Fitzgerald Kennedy').  Not all Party
Names have a NamesBeforeKeyName (e.g. Madonna, Prince).

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>keyname</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The family or surname (aka Last Name) typically used to
index an entry in an alphabetic list, such as 'Michael' in
'George Michael' or 'Kennedy' in 'John Fitzgerald Kennedy'.

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>namesAfterKeyname</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The names following the KeyName (e.g. 'Ibrahim' in 'Anwar
Ibrahim').  This is common in many Asian personal name forms
where the full name begins with the KeyName, which is followed
by other names.

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>bleed</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

Any additions to the Last and First Name such as featuring
artist information or duet partners

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>abbrName</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

A short version of the Party Name for use on devices with
a small display.

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>language</strong></td>
<td valign="top"><a href="#grps_languagecd">GRPS_LanguageCd</a></td>
<td>

The local language context for name

</td>
</tr>
</tbody>
</table>

### GRPS_Product

Defines a Product

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The source system, unique identifier for the Product

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td>

A moniker identifying the source backend service for this instance of a Product

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>contributors</strong></td>
<td valign="top">[<a href="#grps_contribution">GRPS_Contribution</a>!]</td>
<td>

Participants contributing to this Product

</td>
</tr>
</tbody>
</table>

### GRPS_Product_Version

Defines a Prodcut Version

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The source system, unique identifier for the Product Version

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td>

A moniker identifying the source backend service for this instance of a Product Version

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>contributors</strong></td>
<td valign="top">[<a href="#grps_contribution">GRPS_Contribution</a>!]</td>
<td>

Participants contributing to this Product Version

</td>
</tr>
</tbody>
</table>

### GRPS_Recording_Project

Defines a Recording Project

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The source system, unique identifier for the Recording Project

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td>

A moniker identifying the source backend service for this instance of a Recording Project

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>contributors</strong></td>
<td valign="top">[<a href="#grps_contribution">GRPS_Contribution</a>!]</td>
<td>

Participants contributing to this Recording Project

</td>
</tr>
</tbody>
</table>

### GRPS_Repertoire_Owner

A Repertoire Owner

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Song

Defines a Song (aka DDEX MusicalWork)

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The source system, unique identifier for the Song

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td>

A moniker identifying the source backend service for this instance of a Song

</td>
</tr>
</tbody>
</table>

### GRPS_Track

Defines a Track (aka DDEX MusicalWorkSoundRecording)

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

The source system, unique identifier for the Track

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a>!</td>
<td>

A moniker identifying the source backend service for this instance of a Track

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>contributors</strong></td>
<td valign="top">[<a href="#grps_contribution">GRPS_Contribution</a>!]</td>
<td>

Participants contributing to this Track

</td>
</tr>
</tbody>
</table>

### GRPS_User_Message

Defines a localized, ordered user message comment

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>messageType</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>messageText</strong></td>
<td valign="top"><a href="#grps_localstring">GRPS_LocalString</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>participant</strong></td>
<td valign="top"><a href="#grps_participant">GRPS_Participant</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>project</strong></td>
<td valign="top"><a href="#grps_recording_project">GRPS_Recording_Project</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>productVersion</strong></td>
<td valign="top"><a href="#grps_product_version">GRPS_Product_Version</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>product</strong></td>
<td valign="top"><a href="#grps_product_version">GRPS_Product_Version</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>track</strong></td>
<td valign="top"><a href="#grps_track">GRPS_Track</a></td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>updateDt</strong></td>
<td valign="top"><a href="#datetime">Datetime</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>updateBy</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### Participant

Stub - Aggregate Participant Entity

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td>

Universally, unique identifier for backend service Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>source</strong></td>
<td valign="top"><a href="#source">Source</a></td>
<td>

Identifies the source backend service of the Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>GRPS_Participant</strong></td>
<td valign="top"><a href="#grps_participant">GRPS_Participant</a></td>
<td>

Exend Participant to add GRPS_Participant

</td>
</tr>
</tbody>
</table>

## Enums

### ContributorClass

Participant contributor classes or task classes

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>PERFORMANCE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>COMPOSITION</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PRODUCTION</strong></td>
<td></td>
</tr>
</tbody>
</table>

### ImageUsageType

Image Usage Types

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>THUMBNAIL</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>COVER_ART</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>PROFILE</strong></td>
<td></td>
</tr>
</tbody>
</table>

### Source

Identifies the registered backend data sources

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>GRPS</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>CONSOLE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>SPOTIFY</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>APPLE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>GRACENOTE</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>MUSICBRAINZ</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>ORCHARE</strong></td>
<td></td>
</tr>
</tbody>
</table>

## Scalars

### Boolean

The `Boolean` scalar type represents `true` or `false`.

### Date

Defines a calendar date

### Datetime

Defines a point in time (e.g. DateTime)

### ID

The `ID` scalar type represents a unique identifier, often used to refetch an object or as key for a cache. The ID type appears in a JSON response as a String; however, it is not intended to be human-readable. When expected as an input type, any string (such as `"4"`) or integer (such as `4`) input value will be accepted as an ID.

### Int

The `Int` scalar type represents non-fractional signed whole numeric values. Int can represent values between -(2^31) and 2^31 - 1.

### String

The `String` scalar type represents textual data, represented as UTF-8 character sequences. The String type is most often used by GraphQL to represent free-form human-readable text.

### URL

Defines a qualified URL


## Interfaces


### GRPS_ContributorWork

A tagging interface to define an entity for which Participants can contribute to its creation

<table>
<thead>
<tr>
<th align="left">Field</th>
<th align="right">Argument</th>
<th align="left">Type</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2" valign="top"><strong>id</strong></td>
<td valign="top"><a href="#id">ID</a>!</td>
<td></td>
</tr>
</tbody>
</table>
