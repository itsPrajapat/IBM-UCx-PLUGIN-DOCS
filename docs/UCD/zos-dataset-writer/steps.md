
z/OS Dataset Writer - Steps
===========================

# Steps



### Steps





Process steps in the z/OS Dataset Writer plug-in
------------------------------------------------


* 
[Write to Sequential Dataset](#write_to_seq)




#### Write to Sequential Dataset


Use this step to write input text to
 a sequential dataset. **Note:** To create a GDG version add (+1) along with GDG base. An output property 
**DatasetName** will contain the actual GDG version dataset name that is created and can be referred in successive steps
 of the process.




| Name | Type | Description | Required |
| --- | --- | --- | --- |
| Text | String | Text to be 
written in a sequential dataset. | Yes |
| Dataset Name | String | Name of a sequential dataset to write input text. | 
Yes |
| Append | Boolean | Select to append input text in the data set. | No |
| Allocate Data Set | String | Specify 
`TRUE` to allocate a sequential data set with passed parameters. | No |
| Delete Existing Data Set | String | Specify 
`TRUE` to delete the sequential data set if already exist before allocation. | No |
| Volume Serial | String | Leave 
blank to use the system default volume. | No |
| Space Units | Enumeration:
* TRACKS
* CYLINDERS
 | Specify the dataset 
space units. For example, Tracks or Cylinders | Yes |
| Average Record Unit | Enumeration:
* – – –
* K
* M
* U
 | Select
 a unit to use when allocating average record length. The unit **U** specifies single-record units (bytes). **K** 
specifies thousand-record units (kilobytes). **M** specifies million-record units (megabytes). (- – -) specifies the 
system default value. | No |
| Primary Quantity | String | Specify the primary quantity in average record units. | Yes |

| Secondary Quantity | String | Specify the secondary quantity in average record units. | Yes |
| Record Format | 
Enumeration:
* FB
* F
* VB
* V
* FBA
* VBA
* FBM
* FM
* VBM
* VM
 | Specify the record format. | Yes |
| Record Length |
 String | Specify the record length. | Yes |
| Block Size | String | Specify the number of bytes of data to place in 
each block, based on the record length. | Yes |







|Back to ...||Latest Version|z/OS Dataset Writer ||||
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|[All Plugins](../../index.md)|[Deploy Plugins](../README.md)|[2.1132365]()|[Readme](README.md)|[Overview](overview.md)|[Usage](usage.md)|[Downloads](downloads.md)|