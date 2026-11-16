# Foreword

The following files are part of the Redfish development effort:

* [DSP0218](https://www.dmtf.org/dsp/DSP0218) - Platform Level Data Model (PLDM) for Redfish Device Enablement Specification - Binary-encoded JSON (BEJ) and dictionary-based mapping of Redfish schemas and properties into PLDM messages.
* [DSP0266](https://www.dmtf.org/dsp/DSP0266) - Redfish Specification - Main Redfish Specification.
* [DSP0268](https://www.dmtf.org/dsp/DSP0268) - Redfish Data Model Specification - Normative descriptions and additional text for every schema defined in DSP8010 and example payloads for every resource.
* [DSP0270](https://www.dmtf.org/dsp/DSP0270) - Redfish Host Interface Specification - "In-band" or "OS-based" Redfish host interface.
* [DSP0272](https://www.dmtf.org/dsp/DSP0272) - Redfish Interoperability Profiles Specification - Structure and JSON document that is used to define and publish an interoperability profile that checks an implementation's conformance to a defined minimum set of functionality.
* [DSP2043](https://www.dmtf.org/dsp/DSP2043) - Redfish Mockups Bundle - Set of mockups that can be used as sample output from `GET` responses from a Redfish service.  Informative in nature, it was used to develop the schema.  A person can set up an NGINX or similar server and configure it to output JSON format and then use this directory for demonstration purposes.
* [DSP2044](https://www.dmtf.org/dsp/DSP2044) - Redfish White Paper - Non-normative document helping those new to Redfish understand how to interact with the Redfish service and understand common functions and tasks.
* [DSP2046](https://www.dmtf.org/dsp/DSP2046) - Redfish Resource and Schema Guide - Informative documentation regarding common Redfish resource properties and a listing of properties that can be found in each of the Redfish resources.
* [DSP2053](https://www.dmtf.org/dsp/DSP2053) - Redfish Property Guide - Informative documentation providing an index to individual property definitions across all Redfish schema.
* [DSP2065](https://www.dmtf.org/dsp/DSP2065) - Redfish Message Registry Guide - Informative documentation providing details regarding the messages defined in Redfish standard message registries.
* [DSP8010](https://www.dmtf.org/dsp/DSP8010) - Redfish Schema - Redfish schema definitions.  These files are normative in nature and are normatively referenced by the *Redfish Specification*.  The three schema formats are CSDL (OData Common Schema Definition Language format, which is in XML), JSON Schema, and OpenAPI schema.  These schema definitions should be functionally equivalent, thus specifying the schema in three different languages.
* [DSP8011](https://www.dmtf.org/dsp/DSP8011) - Redfish Standard Registries - Redfish registry definitions.  This bundle of Redfish registries includes message registries used for Redfish-defined messages including events and privilege maps.
* [DSP8013](https://www.dmtf.org/dsp/DSP8013) - Redfish Interoperability Profiles Bundle - Bundle of published Redfish interoperability profile documents and supporting schema and sample documents used for creating profiles.

# ANNEX A (informative) Change log

| Registry file              | Version | Date       | Description         |
| :-------                   | :---    | :---       | :------------------ |
| Base                       | 1.25.0  | TBD        | Added `AliasValueConflict` message. |
| Environmental              | 1.6.0   | TBD        | Added `ChassisIntrusionDetected` and `ChassisIntrusionReset` messages. |
| Environmental              | 1.x.x   | TBD        | Errata release.  Clarified that `LeakDetectorDisconnected` applies when a leak detector is disconnected or uninstalled. |
| Platform                   | 1.6.0   | TBD        | Added `PowerOnSequenceFailed`, `CriticalConditionShutdown`, and `BootError` messages. |
| (various files)            | various | TBD        | Errata release.  Corrected `@odata.type` value. |
| AccountSecurity            | 1.2.0   | 2026-08-07 | Added `InsufficientPrivilegeWithAddress` and `InvalidCredentialsWithAddress` messages.  Changed parameter definitions for `InsufficientPrivilege` and `InvalidCredentials` messages. |
| Base                       | 1.24.0  | 2026-08-07 | Added `AliasValueReassigned`, `SoftwareRequired`, `PropertyNotApplicable`, `FailoverInProgress`, and `RedundancyDisabledWrongState` messages. |
| Device                     | 1.0.0   | 2026-08-07 | Initial release. |
| Environmental              | 1.x.x   | 2026-08-07 | Errata release.  Added recommendation to indicate delta pressure or temperature values in arguments for idenifying the source of temperature or pressure readings. |
| EventService               | 1.0.0   | 2026-08-07 | Initial release. |
| ManagerEvent               | 1.2.0   | 2026-08-07 | Added `RedundancyGroupCritical`, `RedundancyGroupWarning`, `RedundancyGroupNormal`, `RedundancyDisabled`, `PeerMissing`, `PeerUnavailable`, `PeerNotProvisioned`, `PeerInvalidState`, `PeerVersionMismatch`, and `ManagerGoingOfflineTemporarily` messages. |
| Platform                   | 1.5.0   | 2026-08-07 | Added `CPUMismatch`, `MemoryParityError`, `MemoryMirroringDegraded`, `MemoryMirroringFailed`, `MemorySparingActivated`, `MemorySparingFailed`, `MemoryTrainingFailed`, `PCIeManagedLinkDown`, `PCIeUncorrectableError`, `PCIeFatalErrorDetected`, `PCIeECRCErrorDetected`, `PCIeReplayTimeoutDetected`, `PCIeCompletionTimeoutDetected`, `PCIeHeaderLogOverflow`, `ThermalSubsystemDegraded`, `ThermalSubsystemRestored`, `PowerSubsystemDegraded`, `PowerSubsystemRestored`, `ThermalTrip`, and `Throttled` messages.  Deprecated `Device` messages in favor of new Device Message Registry. |
| Platform                   | 1.x.x   | 2026-08-07 | Errata release.  Corrected the severity of the `DeviceManagementInterfaceError` and `DeviceManagementInterfaceUnresponsive` messages.  Clarified `PCIeLinkDown` is for surprise link down events. |
| Power                      | 1.4.0   | 2026-08-07 | Added `PowerBrakeApplied` and `PowerBrakeReleased` messages. |
| ServiceCommunications      | 1.2.0   | 2026-08-07 | Added `SecureCommunicationFailure` and `CertificateVerificationFailure` messages. |
| StorageDevice              | 1.7.0   | 2026-08-07 | Added `VolumeCreated`, `VolumeDeleted`, `DriveSecureEraseStarted`, `DriveSecureEraseFailed`, and `DriveSecureEraseCompleted` messages. |
| Update                     | 1.5.0   | 2026-08-07 | Added `UpdatePending`, `AutomaticRecoveryInitiated`, `AutomaticRecoveryFailed`, and `AutomaticRecoverySuccessful` messages. |
| Update                     | 1.4.1   | 2026-08-07 | Errata release.  Corrected the deprecation message for `ApplyFailed`. |
| (various files)            | various | 2026-08-07 | Errata release.  Several typographic and consistency corrections. |
| AccountSecurity            | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| AutomationNodeEvent        | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| Base                       | 1.23.0  | 2026-04-03 | Added `InvalidScheme` message.  Updated quoting of parameters to messages. Added examples to all messages. |
| Base                       | 1.x.x   | 2026-04-03 | Corrected version added for `ResourceInStandby`.  Restored missing Base.1.1.0.json file. |
| Composition                | 1.2.0   | 2026-04-03 | Updated quoting of parameters to messages.  Added examples to all messages. |
| Environmental              | 1.5.0   | 2026-04-03 | Added `DewPointProximityCaution`, `DewPointProximityCritical`, `DewPointProximityNoLongerCritical`, `DewPointProximityNormal`, `CoolantConnectionPairReversed`, `CoolantConnectionsReversed`, and `CoolantConnectionsCorrected` messages.  Added examples for all messages. |
| EthernetFabric             | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| EthernetFabric             | 1.x.x   | 2026-04-03 | Corrected clearing logic references to `MLAGInterfaceDown`. |
| Fabric                     | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| HeartbeatEvent             | 1.2.0   | 2026-04-03 | Added examples to all messages. |
| JobEvent                   | 1.2.0   | 2026-04-03 | Added examples to all messages. |
| License                    | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| LogService                 | 1.2.0   | 2026-04-03 | Added `DiagnosticDataCollectionStarted`, `DiagnosticDataCollectionCompleted`, `DiagnosticDataCollectionFailed`, `DiagnosticDataInvalid`, and `DiagnosticDataBlocked` messages.  Added examples to all messages. |
| ManagerEvent               | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| NetworkDevice              | 1.2.0   | 2026-04-03 | Added examples to all messages. |
| Platform                   | 1.4.0   | 2026-04-03 | Added examples to all messages.  Corrected the `PCIeLinkWidthChange` message. |
| Power                      | 1.3.0   | 2026-04-03 | Added `ChassisPowerLimitExceeded` and `ChassisPowerLimitRestored` messages.  Added examples to all messages. |
| Power                      | 1.x.x   | 2026-04-03 | Errata release.  Corrected quotation mark usage in several messages.  Corrected clearing logic references to `PowerSupplyFailed`. |
| Redfish Privilege Registry | 1.9.0   | 2026-04-03 | Added entries for new `MemoryExtent` and `MemoryExtentCollection` schemas. |
| ResourceEvent              | 1.5.0   | 2026-04-03 | Added `ResourceUnavailable` and `ResourceAvailable` messages.  Updated quoting of parameters to messages.  Added examples to all messages. |
| SensorEvent                | 1.2.0   | 2026-04-03 | Added examples to all messages. |
| ServiceCommunications      | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| StorageDevice              | 1.6.0   | 2026-04-03 | Added examples to all messages.  Fixed a grammatical error in the `BlockSecurityIDRemoved` message. |
| TaskEvent                  | 1.1.0   | 2026-04-03 | Added examples to all messages. |
| Telemetry                  | 1.2.0   | 2026-04-03 | Added examples to all messages. |
| Update                     | 1.4.0   | 2026-04-03 | Added `ActivatingOnComponent`, `StagingOnComponent`, `CleanupOnComponent`, `StageFailed`, and `CleanupFailed` messages.  Deprecated `ApplyingOnComponent` and `ApplyFailed` in favor of `ActivatingOnComponent` and `ActivateFailed`.  Added examples to all messages. |
| Base                       | 1.22.1  | 2025-12-04 | Errata release.  Clarified that `StringValueTooShort` is also used for empty string conditions.  Clarified that `PropertyValueExternalConflict` is used for configuration conflicts on the same service, but managed on a different interface. |
| Environmental              | 1.4.0   | 2025-12-04 | Added `FanWarning`, `CoolingUnitGroupCritical`, `CoolingUnitGroupWarning`, and `CoolingUnitGroupNormal` messages. |
| LogService                 | 1.1.0   | 2025-12-04 | Added `LogCleared` message. |
| ManagerEvent               | 1.0.0   | 2025-12-04 | Initial release. |
| Platform                   | 1.3.2   | 2025-12-04 | Errata release.  Corrected the `ParamTypes` value for `MemoryContainedError`. |
| Power                      | 1.2.0   | 2025-12-04 | Added `PowerDistributionGroupCritical`, `PowerDistributionGroupWarning`, and `PowerDistributionGroupNormal` messages. |
| Base                       | 1.22.0  | 2025-09-05 | Deprecated `AccessForbidden` in favor of the existing `InsufficientPrivilege` message. |
| Environmental              | 1.3.0   | 2025-09-05 | Added `LeakDetectorFailure`, `LeakDetectorConnected`, `LeakDetectorDisconnected`, `LeakDetectorRestored`, `ValveClosed`, `ValveOpened`, `ValvePositionChanged`, `ValveUnableToReachSetPoint`, and `ValveUnableToReachSetPointPercent` messages. |
| Environmental              | 1.x.x   | 2025-09-05 | Errata release.  Corrected the `ClearsMessage` entries for `FanGroupNormal`.  Corrected the `MapsToGeneralMessages` entries for `FanFailed` and `PumpFailed`. |
| HeartbeatEvent             | 1.1.1   | 2025-09-05 | Errata release.  Added missing version tags for the `RedfishServiceStarted` and `RedfishServiceShuttingDown` messages. |
| Platform                   | 1.1.1   | 2025-09-05 | Errata release.  Added missing version tags for the `NVRAMClearAsserted` and `SecurityBypassAsserted` messages. |
| Platform                   | 1.3.1   | 2025-09-05 | Errata release.  Corrected the data type of the `NumberOfArgs` term for many messages.  Removed errant space at the end of the `PCIeLinkRestored` message identifier. |
| Power                      | 1.1.0   | 2025-09-05 | Added `ChassisPoweredOn` and `ChassisPoweredOff` messages. |
| Power                      | 1.0.3   | 2025-09-05 | Errata release.  Corrected the `ClearsMessage` entries for `PowerSupplyGroupNormal`. |
| Redfish Privilege Registry | 1.8.0   | 2025-09-05 | Added entries for new `CertificateEnrollment` and `CertificateEnrollmentCollection` schemas. |
| Redfish Privilege Registry | 1.7.1   | 2025-09-05 | Errata release.  Added missing subordinate override statement for `EthernetInterfaceCollection`. |
| SensorEvent                | 1.1.0   | 2025-09-05 | Added `SensorConnected` and `SensorDisconnected` messages. |
| StorageDevice              | 1.5.1   | 2025-09-05 | Errata release.  Clarified the expected user actions needed for `WriteCacheTemporarilyDegraded` and `WriteCacheDegraded` messages.  Added missing version tags for the `VolumeRebuilding` and `VolumeReconfiguring` messages. |
| Update                     | 1.1.1   | 2025-09-05 | Errata release.  Added missing version tag for the `NoTargetsDetermined` message. |
| Update                     | 1.2.1   | 2025-09-05 | Errata release.  Added missing version tags for the `NoTargetsDetermined`, `UpdateSkipped`, `UpdateSkippedSameVersion`, and `UpdateNotApplicable` messages. |
| Update                     | 1.3.0   | 2025-09-05 | Added `UpdateSkippedVersionTooLow` message. |
| (various files)            |         | 2025-09-05 | Added `Release` property to every minor message registry release, showing the associated DSP8011 release bundle version. |
| AutomationNodeEvent        | 1.0.0   | 2025-05-01 | Initial release. |
| Environmental              | 1.1.1   | 2025-05-01 | Errata release.  Corrected the severity of the `FanFailed` and `PumpFailed` messages. |
| Environmental              | 1.2.0   | 2025-05-01 | Added `PumpSubsystemHealth`, `FilterSubsystemHealth`, `ReservoirSubsystemHealth`, `PrimaryCoolantConnectorSubsystemHealth`, and `SecondaryCoolantConnectorSubsystemHealth` messages. |
| JobEvent                   | 1.1.0   | 2025-05-01 | Added `JobValidationBypassed`, `JobValidationStarted`, `JobValidatedOK`, and `JobValidateException` messages. |
| Platform                   | 1.3.0   | 2025-05-01 | Added `PowerBrake`, `VoltageRegulatorFault`, memory-related, PCIe-related, and device-related messages. |
| Power                      | 1.0.2   | 2025-05-01 | Errata release.  Corrected the severity of the `PowerSupplyFailed` message. |
| Redfish Privilege Registry | 1.7.0   | 2025-05-01 | Added entry for new `VirtualCXLSwitchCollection`, `VirtualCXLSwitch`, `VirtualPCI2PCIBridgeCollection`, `VirtualPCI2PCIBridge`, `AutomationNodeCollection`, `AutomationNode`, `AutomationInstrumentation`, `JobExecutorCollection`, `JobExecutor`, `JobDocumentCollection`, `JobDocument`, `TelemetryData`, `TelemetryDataCollection`, and `UpdateServiceCapabilities` schemas. |
| StorageDevice              | 1.5.0   | 2025-05-01 | Added `VolumeRebuilding` and `VolumeReconfiguring` messages. |
| Telemetry                  | 1.1.0   | 2025-05-01 | Added `TelemetryDataCreated` message. |
| Update                     | 1.2.0   | 2025-05-01 | Added `UpdateSkipped`, `UpdateSkippedSameVersion`, and `UpdateNotApplicable` messages. |
| Base                       | 1.21.0  | 2025-02-05 | Added `PasswordIncorrectLength`, `PasswordReuseTooRecent`, and `PasswordComplexityNotMet` messages. |
| Base                       | 1.20.1  | 2025-02-05 | Errata release.  Clarified the descriptions and message for the `PropertyValueIncorrect` message to show additional usage. |
| AccountSecurity            | 1.0.0   | 2024-11-27 | Initial release. |
| Base                       | 1.20.0  | 2024-11-27 | Added `AccessUnauthorized` and `AccessForbidden` messages. |
| Base                       | 1.19.1  | 2024-11-27 | Errata release.  Clarified that arguments that contain property names should use the RFC6901 JSON pointer format. |
| Environmental              | 1.1.0   | 2024-11-27 | Added new messages related to flow rate, pressure, fluid level, leak detection, pumps, filters, and fluid quality. |
| HeartbeatEvent             | 1.1.0   | 2024-11-27 | Added `RedfishServiceStarted` and `RedfishServiceShuttingDown` messages. |
| HeartbeatEvent             | 1.0.2   | 2024-11-27 | Errata release.  Fixed the reference to the `HeartbeatIntervalMinutes` property in the `RedfishServiceFunctional` message. |
| Platform                   | 1.2.0   | 2024-11-27 | Added `PlatformReset` and `PlatformResetWatchdogTimer` messages. |
| Redfish Privilege Registry | 1.6.0   | 2024-11-27 | Added entry for new `StorageMetrics` schema. |
| ResourceEvent              | 1.4.2   | 2024-11-27 | Errata release.  Clarified that arguments that contain property names should use the RFC6901 JSON pointer format. |
| ServiceCommunications      | 1.0.0   | 2024-11-27 | Initial release. |
| StorageDevice              | 1.4.0   | 2024-11-27 | Added `BlockSecurityIDIssued`, `BlockSecurityIDFailed`, `BlockSecurityIDRemoved` messages. |
| Update                     | 1.1.1   | 2024-11-27 | Errata release.  Corrected the spelling of 'identifier' in various descriptions. |
| Base                       | 1.19.0  | 2024-08-01 | Added `PropertyModified` and `GenerateSecretKeyRequired` messages. |
| ResourceEvent              | 1.4.1   | 2024-08-01 | Errata release.  Added missing `VersionAdded` term to `PropertyValueModifiedByClient`. |
| StorageDevice              | 1.3.0   | 2024-08-01 | Added `DrivePredictedMediaLifeLow` message. |
| Base                       | 1.18.1  | 2024-04-03 | Errata release.  Corrected the number of arguments specified for `ActionParameterValueOutOfRange`. |
| Platform                   | 1.1.0   | 2024-04-03 | Added `NVRAMClearAsserted` and `SecurityBypassAsserted` messages. |
| ResourceEvent              | 1.4.0   | 2024-04-03 | Added `PropertyValueModifiedByClient` message. |
| Update                     | 1.1.0   | 2024-04-03 | Added `NoTargetsDetermined` message.  Updated usage of `VerificationFailed` to include service-level verification. |
| Base                       | 1.18.0  | 2023-11-30 | Added `ActionParameterValueOutOfRange` message. |
| Composition                | 1.1.2   | 2023-11-30 | Errata release.  Corrected the `RegistryVersion` property to match the intended release number. |
| Redfish Privilege Registry | 1.5.0   | 2023-11-30 | Added entries for all missing schemas.  Updated entry for `Session` to use `ConfigureManager` and `ConfigureSelf` for `GET` and `HEAD` operations. |
| Telemetry                  | 1.0.0   | 2023-11-30 | Initial release. |
| (various files)            | various | 2023-11-30 | Errata release.  Several typographic and consistency corrections. |
| Base                       | 1.17.0  | 2023-08-03 | Added `OneTimePasscodeSent` message. |
| Fabric                     | 1.0.1   | 2023-08-03 | Errata release.  Removed the errant trailing space in the `CableOK` message identifier. |
| StorageDevice              | 1.2.0   | 2023-08-03 | Deprecated `VolumeOffine` in favor of new `VolumeOffline` message. |
| Base                       | 1.16.0  | 2023-04-04 | Added `StringValueTooShort`, `ArraySizeTooLong`, `ArraySizeTooShort`, and `LicenseRequired` messages. |
| Environmental              | 1.0.0   | 2023-04-04 | Initial release. |
| License                    | 1.0.2   | 2023-04-04 | Errata release.  Corrected the values for the `ParamTypes` terms to use the defined enumeration values. |
| Platform                   | 1.0.0   | 2023-04-04 | Initial release. |
| Power                      | 1.0.0   | 2023-04-04 | Initial release. |
| Redfish Privilege Registry | 1.4.0   | 2023-04-04 | Added entries for `AttributeRegistry`, `PrivilegeRegistry`, `MessageRegistry`, `ComponentIntegrity`, and `ComponentIntegrityCollection`. |
| ResourceEvent              | 1.3.0   | 2023-04-04 | Added `TestMessage` message. |
| Base                       | 1.15.0  | 2022-12-08 | Added `QueryParameterUnsupported` and `AuthenticationTokenRequired` messages. |
| NetworkDevice              | 1.0.2   | 2022-12-08 | Errata release.  Updated descriptions for identifier arguments to allow for names. |
| Redfish Privilege Registry | 1.3.1   | 2022-12-08 | Errata release.  Added missing `DELETE` privilege to `ManagerDiagnosticData`. |
| Base                       | 1.14.0  | 2022-08-04 | Deprecated `CreateFailedMissingReqProperties` in favor of `PropertyMissing`. |
| Sensor                     | 1.0.0   | 2022-08-04 | Initial release.  Defines messages for events from the sensor model. |
| Base                       | 1.13.0  | 2022-04-07 | Added `HeaderMissing`, `HeaderInvalid`, `OperationNotAllowed`, `PayloadTooLarge`, `InsufficientStorage`, `MissingOrMalformedPart`, and `EventBufferExceeded` messages. |
| Base                       | 1.12.2  | 2022-04-07 | Corrected the `NumberOfArguments` term in the `PropertyValueDeprecated` message. |
| License                    | 1.0.1   | 2022-04-07 | Corrected the values for the `NumberOfArguments` terms to be integers rather than strings. |
| Redfish Privilege Registry | 1.3.0   | 2022-04-07 | Added entry for `ManagerDiagnosticData`. |
| ResourceEvent              | 1.2.1   | 2022-04-07 | Added argument descriptions to the `LicenseChanged` message. |
| Update                     | 1.0.1   | 2022-04-07 | Corrected the values for the `NumberOfArguments` terms to be integers rather than strings. |
| ResourceEvent              | 1.2.0   | 2021-12-02 | Added `AggregationSourceDiscovered` message. |
| ResourceEvent              | 1.1.1   | 2021-12-02 | Errata release.  Corrected the version number of the registry. |
| StorageDevice              | 1.1.0   | 2021-12-02 | Added `BatteryOK`, `BatteryCharging`, `BatteryMissing`, `BatteryFailure`, `ControllerDegraded`, `ControllerPreviousError`, `ControllerPasswordAccepted`, `ControllerPasswordRequired`, `ControllerPortOK`, `ControllerPortDegraded`, `ControllerPortFailure`, `DriveMissing`, `DriveMissingCleared`, `DriveOffline`, `DriveOfflineCleared`, `VolumeOffline`, and `VolumeOfflineCleared` messages. |
| StorageDevice              | 1.0.1   | 2021-12-02 | Errata release.  Clarified various messages reflecting health changes that specifically the health of the device is changing. |
| Base                       | 1.12.0  | 2021-10-06 | Added `ActionParameterValueConflict`, `ResetRecommended`, and `PropertyNotUpdated` messages.  Expanded the scope of `ResetRequired` for cases where clients may need to recover from errors reported on a resource. |
| Base                       | 1.x.x   | 2021-10-06 | Errata release.  Added `PropertyValueOutOfRange` to versions where it was removed by mistake.  Corrected argument character in `InvalidJSON`. |
| Composition                | 1.1.1   | 2021-10-06 | Errata release.  Added version information to messages. |
| License                    | 1.0.0   | 2021-10-06 | Initial release. |
| ResourceEvent              | 1.1.0   | 2021-10-06 | Added `ResourceStateChanged`, `ResourcePoweredOn`, `ResourcePoweringOn`, `ResourcePoweredOff`, `ResourcePoweringOff`, and `ResourcePaused` messages.  Deprecated `LicenseExpired`, `LicenseChanged`, and `LicenseAdded` for messages in the License Message Registry. |
| Redfish Privilege Registry | 1.2.0   | 2021-10-06 | Added entries for all resources defined by Redfish since the previous release of the registry. |
| HeartbeatEvent             | 1.0.0   | 2021-08-05 | Initial release. |
| Base                       | 1.11.0  | 2021-08-05 | Added `NetworkNameResolutionNotConfigured`, `NetworkNameResolutionNotSupported`, `ServiceDisabled` messages. |
| Base                       | 1.10.1  | 2021-08-05 | Added missing `ParamTypes` property to `UndeterminedFault`. |
| Update                     | 1.0.0   | 2021-04-06 | Initial release. |
| Base                       | 1.10.0  | 2021-04-06 | Added `InvalidURI`, `PropertyDeprecated`, `ResourceDeprecated`, `PropertyValueDeprecated`, `ActionDeprecated`, `ActionParameterValueNotInList`, `PropertyValueResourceConflict`, and `PropertyValueExternalConflict` messages. |
| Composition                | 1.1.0   | 2021-04-06 | Added `EmptyManifest`, `UnableToProcessStanzaRequest`, `ResourceBlockInvalid`, `ResourceBlockNotFound`, `NoResourceMatch`, `IncompatibleZone`, `SpecifiedResourceAlreadyReserved`, and `ConstrainedResourceAlreadyReserved` messages. |
| EthernetFabric             | 1.0.0   | 2020-12-01 | Initial release.  Defines messages for Ethernet fabrics. |
| Fabric                     | 1.0.0   | 2020-12-01 | Initial release.  Defines messages for general fabrics. |
| Base                       | 1.9.0   | 2020-12-01 | Added `UndeterminedFault`, `ConditionInRelatedResource`, `RestrictedRole`, `RestrictedPrivilege`, and `StrictAccountTypes` messages. |
| Task                       | 1.0.3   | 2020-12-01 | Errata release.  Clarified descriptions to specify `TaskState` values. |
| JobEvent                   | 1.0.0   | 2020-08-04 | Initial release.  Defines messages for jobs. |
| LogService                 | 1.0.0   | 2020-08-04 | Initial release.  Defines messages for log services. |
| Redfish Privilege Registry | 1.1.0   | 2020-08-04 | Added entries for all resources defined by Redfish. |
| Base                       | 1.8.2   | 2020-08-04 | Errata release.  Clarified the `GeneralError` message to direct clients to either the `Resolution` property or `@Message.ExtendedInfo`.  Added descriptions to arguments for all messages. |
| StorageDevice              | 1.0.0   | 2020-04-30 | Initial release.  Defines messages for storage devices. |
| Base                       | 1.8.1   | 2020-04-30 | Errata release.  Updated to MessageRegistry v1.4.0 schema. |
| Composition                | 1.0.1   | 2020-04-30 | Errata release.  Added descriptions to arguments and updated to MessageRegistry v1.4.0 schema. |
| NetworkDevice              | 1.0.1   | 2020-04-30 | Errata release.  Added descriptions to arguments and updated to MessageRegistry v1.4.0 schema. |
| ResourceEvent              | 1.0.3   | 2020-04-30 | Errata release.  Added descriptions to arguments and updated to MessageRegistry v1.4.0 schema. |
| TaskEvent                  | 1.0.2   | 2020-04-30 | Errata release.  Added descriptions to arguments and updated to MessageRegistry v1.4.0 schema. |
| Base                       | 1.8.0   | 2020-03-27 | Added `MaximumErrorsExceeded`, `PreconditionFailed`, `PreconditionRequired`, `OperationFailed`, and `OperationTimeout`  messages. |
| NetworkDevice              | 1.0.0   | 2020-03-27 | Initial release. |
| Base                       | 1.7.0   | 2019-12-06 | Added `PropertyValueIncorrect` and `ResourceCreationConflict` messages. |
| Base                       | 1.6.1   | 2019-10-11 | Errata release.  Fixed typo in the resolution for the `NoValidSession` message. |
| Redfish Privilege Registry | 1.0.4   | 2019-10-11 | Errata release.  Corrected privileges for the `AccountService` and `Session` resources to show that anyone can read the account collection in order to find their own account, add to the session collection, and delete their own session.  Added `NoAuth` to allowed privileges for the service root. |
| Base                       | 1.6.0   | 2019-08-08 | Added `QueryNotSupportedOnOperation`, `ResetRequired`, `PropertyValueConflict`, `ChassisPowerStateOnRequired`, and `ChassisPowerStateOffRequired` messages. |
| Composition                | 1.0.0   | 2019-08-08 | Initial release.  Defines messages to use for composition events. |
| ResourceEvent              | 1.0.2   | 2019-08-08 | Errata release.  Corrected and clarified the description and message strings for all messages.  Removed `CorrespondingMessage` property from all messages. |
| Base                       | 1.5.0   | 2019-04-03 | Added `SubscriptionTerminated` and `PasswordChangeRequired` messages. |
| ResourceEvent              | 1.0.1   | 2018-11-29 | Corrected `@odata.type` and `Id` property formats.  Corrected cases where `ParamTypes` was incorrectly using `value`. |
| TaskEvent                  | 1.0.1   | 2018-11-29 | Corrected `@odata.type` and `Id` property formats.  Corrected cases where `ParamTypes` was incorrectly using `value`.  Fixed spelling of the `TaskProgressChanged` event. |
| ResourceEvent              | 1.0.0   | 2018-08-10 | Initial release.  Defines messages to use for resource events. |
| TaskEvent                  | 1.0.0   | 2018-08-10 | Initial release.  Defines messages to use for task events. |
| Base                       | 1.4.0   | 2018-08-10 | Added `NoOperation` message. |
| Base                       | 1.3.1   | 2018-08-10 | Errata release.  Clarified description and message text for `GeneralError`.  Implementations are expected to provide specific `Resolution` for this message. |
| Redfish Privilege Registry | 1.0.3   | 2018-08-10 | Errata release.  Corrected `ConfigureComponents` plurality privilege throughout.  Corrected JSON object structure throughout. |
| Base                       | 1.3.0   | 2018-04-05 | Added `PropertyValueOutOfRange` and `SessionTerminated` messages. |
| Base                       | 1.2.0   | 2017-08-18 | Added `ResourceNotFound`, `ResourceExhaustion`, `StringValueTooLong` and `EmptyJSON` messages.  Clarified description for `PropertyValueFormatError`.  Corrected parameters for `ResourceAlreadyExists`. |
| Redfish Privilege Registry | 1.0.2   | 2017-08-18 | Errata release.  Corrected `ConfigureUsers` plurality privilege throughout. |
| Base                       | 1.1.0   | 2017-05-19 | Added `ResourceInStandby` message. |
| Redfish Privilege Registry | 1.0.1   | 2017-05-19 | Initial release. |
| Base                       | 1.0.0   | 2015-11-25 | Initial release. |
