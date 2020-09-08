# Code list values

**Purpose**: Verify whether all attributes whose value type is a code list take the values set out therein

**Prerequisites**

**Test method**

When an attribute has a code list as its type, verify that the values comply with the definitions and include the values set out in Annex II, III and IV of the Implementing Rule. To pass this test verify that any instance of an attribute:

* takes only values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'none'.
* takes only a value explicitly specified in the INSPIRE code list register or shall take a value that is narrower (i.e. more specific) than those explicitly specified in the application schema when the code list‘s extensibility is 'narrower'.
* takes values explicitly specified in the INSPIRE code list register when the code list‘s extensibility is 'open' or if a value is not one of the values listed in the code list register check that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule and that all extensions conform to the requirements (This last check is a manual test).

The following checks are performed for every feature in the dataset, for the not extensible codelists:

* Check that all the [referenceSpeciesScheme](#referenceSpeciesScheme) elements has a xlink:href attribute pointing to a [valid value](#validValue1). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [referenceSpeciesId](#referenceSpeciesId) elements has a xlink:href attribute pointing to a [valid value](#validValue2). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [qualifier](#qualifier) elements (if present) has a xlink:href attribute pointing to a [valid value](#validValue3). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).

* Check that all the [countingMethod](#countingMethod) elements (if present) has a xlink:href attribute pointing to a [valid value](#validValue4). If the check fails report [disallowedCodeListValue](#disallowedCodeListValue).


| <a name="validValue1"></a> Valid values for xlink:href attribute of [referenceSpeciesScheme](#referenceSpeciesScheme) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/ReferenceSpeciesSchemeValue | 

| <a name="validValue2"></a> Valid values for xlink:href attribute of [referenceSpeciesId](#referenceSpeciesId) element are available in the INSPIRE Registry. Note: The following codelists are externally governed.| 
| ---- | 
| https://inspire.ec.europa.eu/codelist/EuNomenCodeValue <br> https://inspire.ec.europa.eu/codelist/EunisSpeciesCodeValue <br> https://inspire.ec.europa.eu/codelist/NatureDirectivesCodeValue|

| <a name="validValue3"></a> Valid values for xlink:href attribute of [qualifier](#qualifier) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/QualifierValue | 

| <a name="validValue4"></a> Valid values for xlink:href attribute of [countingMethod](#countingMethod) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/CountingMethodValue | 


The following check is performed for every feature in the dataset, for the open codelist:

* Check that all the [occurrenceCategory](#occurrenceCategory) elements has a xlink:href attribute pointing to a [pre-defined value](#preDefinedValue). If the check fails a manual check will be required asking to review the code list definition in order to verify that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule.

| <a name="preDefinedValue"></a> Pre-defined values for xlink:href attribute of [occurrenceCategory](#occurrenceCategory) element are available in the INSPIRE Registry| 
| ---- | 
| http://inspire.ec.europa.eu/codelist/OccurrenceCategoryValue | 


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (1)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (2)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)
* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (4)

**Test type**: Automated + Manual check (if required)

**Notes**

The following is not applicable for this application schema as no extensions are allowed. It is still included here as a reminder in case extensions will be allowed in the future:

Inspect the code list valued property elements. If a value is not one of the values listed above, review the code list definition to check that any extensions do not overlap with the code lists that are defined in Annexes II, III and IV of the Implementing Rule and that all extensions conform to the requirements. This is a manual test.

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
disallowedCodeListValue <a name="disallowedCodeListValue"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that is not one of the allowed values listed at $codelist. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression				|Multiplicity       |Voidable
---------------------------------------------------------- | -------------------------------|-------------------|---------
referenceSpeciesScheme <a name="referenceSpeciesScheme"></a>   | //schema-element(sd:SpeciesDistributionUnit)/sd:speciesName/sd:SpeciesNameType/sd:referenceSpeciesScheme | 1 | No
referenceSpeciesId <a name="referenceSpeciesId"></a>   | //schema-element(sd:SpeciesDistributionUnit)/sd:speciesName/sd:SpeciesNameType/sd:referenceSpeciesId | 1 | No
qualifier <a name="qualifier"></a> | //schema-element(sd:SpeciesDistributionUnit)sd:speciesName/sd:SpeciesNameType/sd:qualifier | 0..1 | Yes
countingMethod <a name="countingMethod"></a> | //schema-element(sd:SpeciesDistributionUnit)/sd:distributionInfo/sd:DistributionInfoType/sd:populationSize/sd:PopulationSizeType/sd:countingMethod | 1 (The parent is optional) | No
occurrenceCategory <a name ="occurrenceCategory"></a>	| //schema-element(sd:SpeciesDistributionUnit)/sd:distributionInfo/sd:DistributionInfoType/sd:occurrenceCategory/@xlink:href | 1 (The parent is optional) | No
