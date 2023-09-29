<p align="center">
  <img src="http://redfish.dmtf.org/sites/all/themes/dmtf2015/images/dmtf-redfish-logo.png" alt="DMTF Redfish" width=180></p>

# Redfish publications

This repository contains official read-only copies of published DMTF Redfish schemas and message registries.  

This replicates the contents of DMTF publications DSP8010 and DSP8011, with release tags that match the publication versions.

Issues and pull requests cannot be created in this repository.  Issues, questions, and enhancement requests are encouraged, and should be directed to the public [Redfish Forum](https://www.redfishforum.com), or submitted as feedback to the DMTF via the [Feedback and Technology Submission Portal](https://www.dmtf.org/standards/feedback).

Employees of DMTF member companies should contact their representative, or join the working group to actively participate in the development of future Redfish releases.

The folders of this repository contain the following materials:

* `csdl` - Redfish schema files, from DSP8010, in OData CSDL XML format
* `dictionaries` - RDE dictionary files from DSP8010
* `json-schema` - Redfish schema files, from DSP8010, in JSON Schema format
* `openapi` - Redfish schema files, from DSP8010, in OpenAPI YAML format
* `registries` - Redfish standard message registries from DSP8011

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
