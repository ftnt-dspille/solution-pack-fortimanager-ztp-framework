| [Home](../README.md) |
|----------------------|

# Upgrade from 1.0.x to 1.2.0+

Upgrading from version 1.0.x to 1.2.0+ changes some field types that cannot be directly converted. This requires administrative pre-setup steps before performing an upgrade to be successful. If you have records the `Managers`, `Devices`, `Metafield Templates`, `Scripts`, or `ZTP Profile` then you need to export these records using the steps in `Pre-Steps Steps to Preserve Existing Records` before performing the upgrade. 

## Pre-Steps Steps to Preserve Existing Records

If you do not have any records, or existing data, that you need to save you can skip this step and move on to `Pre-Steps before Upgrade to 1.2.0+` below. 

1. Download the Export Template [ExportTemplates-ZTPF-Records.json](./ExportTemplates-ZTPF-Records.json). 
2. In FortiSOAR, as an Administrator, navigate to `System Settings` and `Export Wizard`.
3. Click the `Import Template` button and upload the `ExportTemplates-ZTPF-Records.json` file. 
4. Run the Template `ZTPF-Export-Records` and save the zip file created to your local disk. 
5. Next, perform the Steps in `Pre-Steps before Upgrade to 1.2.0+`. 

## Pre-Steps before Upgrade to 1.2.0+

In these steps will we simply remove fields that will be modified by the upgrade. 

1. In FortiSOAR, as an Administrator, navigate to `System Settings` and `Modules`
2. Select the following `Modules` and delete the respective fields listed below. Click Save when you delete the fields but **do not click** `Publish All Modules` yet. 
  - **Devices**:
    - `Source Data`
    - `Device Metadata`
  - **Manager**:
    - `Manager Metadata`
    - `Source Data`
  - **Metafield Template**:
    - `Metadata Sources`
  - **Script**:
    - `Metadata Sources`
  - **ZTP Profile**:
    - `Assignment Search Metadata Sources`
    - `ZTP Step Map`
    - `Device Metadata Monitor Regex`
3. Now click `Publish All Modules` to remove the fields. Wait for the system to recover. 
4. Perform the upgrade of the Solution Pack from the `Connectors` and `Content Hub`.

## Post Upgrade Steps to Restore Records

If you performed the steps in `Pre-Steps Steps to Preserve Existing Records` and `Pre-Steps before Upgrade to 1.2.0+` you should now be upgraded and ready to restore your record data. 

1. In FortiSOAR, as an Administrator, navigate to `System Settings` and `Import Wizard`.
2. Click the `Import from File` button and upload the file downloaded from the `ZTPF-Export-Records` Template. 
3. Leave settings as default, `Overwrite if Record Exists`, and confirm records were imported ok. 