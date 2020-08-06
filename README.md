# Schema Types

<details>
  <summary><strong>Table of Contents</strong></summary>

  * [Query](#query)
  * [Objects](#objects)
    * [GRPS_Comment](#grps_comment)
    * [GRPS_ContentLink](#grps_contentlink)
    * [GRPS_CountryCd](#grps_countrycd)
    * [GRPS_DataSourceCd](#grps_datasourcecd)
    * [GRPS_Image](#grps_image)
    * [GRPS_LangCd](#grps_langcd)
    * [GRPS_LocalString](#grps_localstring)
    * [GRPS_Member](#grps_member)
    * [GRPS_Participant](#grps_participant)
    * [GRPS_ParticipantType](#grps_participanttype)
    * [GRPS_PartyGeneralInfo](#grps_partygeneralinfo)
    * [GRPS_PartyName](#grps_partyname)
    * [Participant](#participant)
  * [Enums](#enums)
    * [DataSource](#datasource)
    * [ImageUsageType](#imageusagetype)
    * [TSize](#tsize)
  * [Scalars](#scalars)
    * [Boolean](#boolean)
    * [Date](#date)
    * [Datetime](#datetime)
    * [ID](#id)
    * [Int](#int)
    * [String](#string)
    * [URL](#url)

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
1. Search for matching Participant from the GRPS backend service
2. Return GRPS_Participant type for each matching GRPS Participant
3. A reference to a extParticipants field causes the federation to delegate to RDX service using GRPS Participant id and source
4. RDX service finds all external Participants (id and source) mapped to the GRPS Participant
4. A reference to a Spotify Participant field on the external Participant causes the federation to delegate to SPOT_Participant field
5. The result is a GRPS Participant with a collection of external linked Participants

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

Defines a a localized, ordered entity comment

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
<td colspan="2" valign="top"><strong>seqNo</strong></td>
<td valign="top"><a href="#int">Int</a>!</td>
<td></td>
</tr>
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
<td valign="top"><a href="#datasource">DataSource</a>!</td>
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
<td valign="top"><a href="#datasource">DataSource</a>!</td>
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
<td colspan="2" valign="top"><strong>size</strong></td>
<td valign="top"><a href="#tsize">TSize</a>!</td>
<td></td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>usage</strong></td>
<td valign="top"><a href="#imageusagetype">ImageUsageType</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_LangCd

A system-specific, unique identifier for an entity

type ExtID{
id: String!
source: DataSource!
}

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
<td colspan="2" valign="top"><strong>tag</strong></td>
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
<td colspan="2" valign="top"><strong>lang</strong></td>
<td valign="top"><a href="#grps_langcd">GRPS_LangCd</a>!</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_Member

Member of Band Or Group

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
<td valign="top"><a href="#grps_datasourcecd">GRPS_DataSourceCd</a>!</td>
<td>

Defines the type of membership for a participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>member</strong></td>
<td valign="top"><a href="#grps_participant">GRPS_Participant</a>!</td>
<td>

Identifies the parent Participant in a memberOf relation
or a member in a members relationhip.

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
<td valign="top"><a href="#datasource">DataSource</a>!</td>
<td>

A moniker identifying the source for this instance of a Participant

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>extParticipants</strong></td>
<td valign="top">[<a href="#participant">Participant</a>!]</td>
<td>

A collection of linked, external Participant Entities

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
<td colspan="2" valign="top"><strong>localizedNames</strong></td>
<td valign="top">[<a href="#grps_partyname">GRPS_PartyName</a>!]</td>
<td>

A collection of localized names for the primary name of Participant

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
<td colspan="2" valign="top"><strong>partType</strong></td>
<td valign="top"><a href="#grps_participanttype">GRPS_ParticipantType</a>!</td>
<td>

Defines the type of Paricipant (e.g. Person, Individual,
Band or Compound Artist). This is a key table for valid
Participant Types

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>memberOf</strong></td>
<td valign="top">[<a href="#grps_member">GRPS_Member</a>!]</td>
<td>

If the Participant is a member of a Band or Group

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>members</strong></td>
<td valign="top">[<a href="#grps_member">GRPS_Member</a>!]</td>
<td>

If ther Particpant is a Band, Group with Members

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>similarParticipants</strong></td>
<td valign="top">[<a href="#grps_participant">GRPS_Participant</a>!]</td>
<td>

Similar Artists

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>isOrganziation</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

A flag indicating whether the Participant is an Organization or an
Individual

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>affliation</strong></td>
<td valign="top"><a href="#string">String</a></td>
<td>

Identifies the affilation for the Participant

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
<td colspan="2" valign="top"><strong>localTitles</strong></td>
<td valign="top">[<a href="#grps_localstring">GRPS_LocalString</a>!]</td>
<td></td>
</tr>
</tbody>
</table>

### GRPS_PartyGeneralInfo

General or Background information for a Party

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
<td colspan="2" valign="top"><strong>gender</strong></td>
<td valign="top"><a href="#string">String</a>!</td>
<td>

The Gender of the Party

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
<td colspan="2" valign="top"><strong>birthPlace</strong></td>
<td valign="top"><a href="#string">String</a></td>
<td>

Birth Place

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>residency</strong></td>
<td valign="top"><a href="#grps_countrycd">GRPS_CountryCd</a></td>
<td>

The country of main residency for the Participant

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
<td colspan="2" valign="top"><strong>comments</strong></td>
<td valign="top">[<a href="#grps_comment">GRPS_Comment</a>!]</td>
<td>

Notes and comments regarding Participant

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
normally appears in an alphabetic indix, with
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
<td colspan="2" valign="top"><strong>isNickname</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

Flag to indicate whether a given name is a nickname.  A
nickname is a substitue for the proper name (e.g. 'Pete'
for 'Peter').  Not to be confused with a stage name or
psyeudonym name.

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>isStageName</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

Flag to indicate whether the given name is a stage name or
psyeudonym name

</td>
</tr>
<tr>
<td colspan="2" valign="top"><strong>isLegalName</strong></td>
<td valign="top"><a href="#boolean">Boolean</a>!</td>
<td>

Flag to indicate whether the full name is the legal name

</td>
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
<td valign="top"><a href="#datasource">DataSource</a></td>
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

### DataSource

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

### TSize

T-Shirt Sizing for Images

<table>
<thead>
<th align="left">Value</th>
<th align="left">Description</th>
</thead>
<tbody>
<tr>
<td valign="top"><strong>S</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>M</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>L</strong></td>
<td></td>
</tr>
<tr>
<td valign="top"><strong>XL</strong></td>
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

