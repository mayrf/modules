# sealed-secrets

## Index

- v1alpha1
  - [BitnamiComV1alpha1SealedSecretSpec](#bitnamicomv1alpha1sealedsecretspec)
  - [BitnamiComV1alpha1SealedSecretSpecTemplate](#bitnamicomv1alpha1sealedsecretspectemplate)
  - [BitnamiComV1alpha1SealedSecretSpecTemplateMetadata](#bitnamicomv1alpha1sealedsecretspectemplatemetadata)
  - [BitnamiComV1alpha1SealedSecretStatus](#bitnamicomv1alpha1sealedsecretstatus)
  - [BitnamiComV1alpha1SealedSecretStatusConditionsItems0](#bitnamicomv1alpha1sealedsecretstatusconditionsitems0)
  - [SealedSecret](#sealedsecret)

## Schemas

### BitnamiComV1alpha1SealedSecretSpec

SealedSecretSpec is the specification of a SealedSecret.

#### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**data**|str|Data is deprecated and will be removed eventually. Use per-value EncryptedData instead.||
|**encryptedData** `required`|{str:str}|encrypted data||
|**template**|[BitnamiComV1alpha1SealedSecretSpecTemplate](#bitnamicomv1alpha1sealedsecretspectemplate)|template||
### BitnamiComV1alpha1SealedSecretSpecTemplate

Template defines the structure of the Secret that will be created from this sealed secret.

#### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**data**|{str:str}|Keys that should be templated using decrypted data.||
|**immutable**|bool|Immutable, if set to true, ensures that data stored in the Secret cannot<br />be updated (only object metadata can be modified).<br />If not set to true, the field can be modified at any time.<br />Defaulted to nil.||
|**metadata**|[BitnamiComV1alpha1SealedSecretSpecTemplateMetadata](#bitnamicomv1alpha1sealedsecretspectemplatemetadata)|metadata||
|**type**|str|||
### BitnamiComV1alpha1SealedSecretSpecTemplateMetadata

Standard object's metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#metadata

#### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**annotations**|{str:str}|annotations||
|**finalizers**|[str]|finalizers||
|**labels**|{str:str}|labels||
|**name**|str|name||
|**namespace**|str|namespace||
### BitnamiComV1alpha1SealedSecretStatus

SealedSecretStatus is the most recently observed status of the SealedSecret.

#### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**conditions**|[[BitnamiComV1alpha1SealedSecretStatusConditionsItems0](#bitnamicomv1alpha1sealedsecretstatusconditionsitems0)]|Represents the latest available observations of a sealed secret's current state.||
|**observedGeneration**|int|ObservedGeneration reflects the generation most recently observed by the sealed-secrets controller.||
### BitnamiComV1alpha1SealedSecretStatusConditionsItems0

SealedSecretCondition describes the state of a sealed secret at a certain point.

#### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**lastTransitionTime**|str|Last time the condition transitioned from one status to another.||
|**lastUpdateTime**|str|The last time this condition was updated.||
|**message**|str|A human readable message indicating details about the transition.||
|**reason**|str|The reason for the condition's last transition.||
|**status** `required`|str|Status of the condition for a sealed secret.<br />Valid values for "Synced": "True", "False", or "Unknown".||
|**type** `required`|str|||
### SealedSecret

SealedSecret is the K8s representation of a "sealed Secret" - a regular k8s Secret that has been sealed (encrypted) using the controller's key.

#### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**apiVersion** `required` `readOnly`|"bitnami.com/v1alpha1"|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources|"bitnami.com/v1alpha1"|
|**kind** `required` `readOnly`|"SealedSecret"|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#types-kinds|"SealedSecret"|
|**metadata**|[ObjectMeta](#objectmeta)|metadata||
|**spec** `required`|[BitnamiComV1alpha1SealedSecretSpec](#bitnamicomv1alpha1sealedsecretspec)|spec||
|**status**|[BitnamiComV1alpha1SealedSecretStatus](#bitnamicomv1alpha1sealedsecretstatus)|status||
<!-- Auto generated by kcl-doc tool, please do not edit. -->
