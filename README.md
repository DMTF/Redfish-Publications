<p align="center">
  <img src="http://redfish.dmtf.org/sites/all/themes/dmtf2015/images/dmtf-redfish-logo.png" alt="DMTF Redfish" width=180></p>

# Redfish publications

This repository contains official copies of published DMTF Redfish schemas and message registries.

This replicates the contents of DMTF publications DSP8010 and DSP8011, with release tags that match the publication versions.

Non-DMTF members may file issues and create pull requests to propose changes to the Redfish standard message registries (DSP8011).
This includes proposals for entirely new message registries as well as new messages to existing registries.

For other content, issues, questions, and enhancement requests are encouraged, and should be directed to the public [Redfish Forum](https://www.redfishforum.com), or submitted as feedback to the DMTF via the [Feedback and Technology Submission Portal](https://www.dmtf.org/standards/feedback).

Employees of DMTF member companies should contact their representative, or join the working group to actively participate in the development of future Redfish releases.

The folders of this repository contain the following materials:

* `csdl` - Redfish schema files, from DSP8010, in OData CSDL XML format
* `dictionaries` - RDE dictionary files from DSP8010
* `json-schema` - Redfish schema files, from DSP8010, in JSON Schema format
* `openapi` - Redfish schema files, from DSP8010, in OpenAPI YAML format
* `messages` - Primary copy of Redfish standard message registries from DSP8011; used to generate the contents of the `registries` directory
* `registries` - Redfish standard message registries from DSP8011

# Proposing changes to DSP8011

To propose changes to the Redfish standard message registries (DSP8011):

1) File an issue with proposed new messages, new registries, or fixes to existing messages.  Provide use cases and other justifications for the proposal in the issue.
2) DMTF will review and provide feedback on the issue during DMTF meetings.
3) If the issue is approved, create a branch and make a pull request with the proposed changes.
    * Changes are made in the `messages` directory.
    * Update `Release` term appropriately if a new release is not yet staged.
    * When adding new messages, increment the minor version of `RegistryVersion` if a new version is not yet staged.  Ensure the new message contains the `VersionAdded` term.
    * When editing existing messages, increment the errata version of `RegistryVersion` if a new version is not yet staged.
4) DMTF will review and provide feedback on the pull request during DMTF meetings, and may make edits appropriately.
5) If the pull request is approved, it will merge to the 'staging' branch.

# Staging process

Once a pull request is approved, it is merged into the 'staging' branch.
This does not automatically make the contribution part of a DMTF standard.
The tagged version of the 'main' branch remains the approved, normative material.

DMTF processes require DMTF board approval prior to publication.
Once approved, the 'staging' branch merges to 'main', and is then tagged for the appropriate release.

# Links to additional DMTF Redfish publications

The following files are part of the Redfish development effort:

* [DSP0218](https://www.dmtf.org/dsp/DSP0218) - Platform Level Data Model (PLDM) for Redfish Device Enablement Specification - Binary-encoded JSON (BEJ) and dictionary-based mapping of Redfish schemas and properties into PLDM messages.
* [DSP0266](https://www.dmtf.org/dsp/DSP0266) - Redfish Specification - Main Redfish Specification.
* [DSP0268](https://www.dmtf.org/dsp/DSP0268) - Redfish Data Model Specification - Normative descriptions and additional text for every schema defined in DSP8010 and example payloads for every resource.
* [DSP0270](https://www.dmtf.org/dsp/DSP0270) - Redfish Host Interface Specification - "In-band" or "OS-based" Redfish host interface.
* [DSP0272](https://www.dmtf.org/dsp/DSP0272) - Redfish Interoperability Profiles Specification - Structure and JSON document that is used to define and publish an interoperability profile that checks an implementation's conformance to a defined minimum set of functionality.
* [DSP2043](https://www.dmtf.org/dsp/DSP2043) - Redfish Mockups Bundle - Set of mockups that can be used as sample output from `GETs` from a Redfish service.  Informative in nature, it was used to develop the schema.  A person can set up an NGINX or similar server and configure it to output JSON format and then use this directory for demonstration purposes.
* [DSP2044](https://www.dmtf.org/dsp/DSP2044) - Redfish White Paper - Non-normative document helping those new to Redfish understand how to interact with the Redfish service and understand common functions and tasks.
* [DSP2046](https://www.dmtf.org/dsp/DSP2046) - Redfish Resource and Schema Guide - Informative documentation regarding common Redfish resource properties and a listing of properties that can be found in each of the Redfish resources.
* [DSP2053](https://www.dmtf.org/dsp/DSP2053) - Redfish Property Guide - Informative documentation providing an index to individual property definitions across all Redfish schema.
* [DSP2065](https://www.dmtf.org/dsp/DSP2065) - Redfish Message Registry Guide - Informative documentation providing details regarding the messages defined in Redfish standard message registries.
* [DSP8010](https://www.dmtf.org/dsp/DSP8010) - Redfish Schema - Redfish schema definitions.  These files are normative in nature and are normatively referenced by the *Redfish Specification*.  The three schema formats are CSDL (OData Common Schema Definition Language format, which is in XML), JSON Schema, and OpenAPI schema.  These schema definitions should be functionally equivalent, thus specifying the schema in three different languages.
* [DSP8011](https://www.dmtf.org/dsp/DSP8011) - Redfish Standard Registries - Redfish registry definitions.  This bundle of Redfish registries includes message registries used for Redfish-defined messages including events and privilege maps.
* [DSP8013](https://www.dmtf.org/dsp/DSP8013) - Redfish Interoperability Profiles Bundle - Bundle of published Redfish interoperability profile documents and supporting schema and sample documents used for creating profiles.
