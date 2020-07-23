# Code lists

**Purpose**: Verify that code lists extensions can be accessed.

**Prerequisites**

**Test method**

* Verify that any code list extensions are publicly accessible via HTTP, i.e. inspect extensible code list values property elements. If a reference (@xlink:href) has a value that does not start with http://inspire.ec.europa.eu/codelist/, verify that a HTTP GET request to the URI retrieves a document. Otherwise report [brokenLink](#brokenLink).

This data theme currently has the following extensible code lists:

* [GeneralCountingUnitValue](#GeneralCountingUnitValue) : https://inspire.ec.europa.eu/codelist/GeneralCountingUnitValue

* [Article17CountingUnitValue](#Article17CountingUnitValue) :  https://inspire.ec.europa.eu/codelist/Article17CountingUnitValue

* [LocalSpeciesNameCodeValue](#LocalSpeciesNameCodeValue) : https://inspire.ec.europa.eu/codelist/LocalSpeciesNameCodeValue

* [OccurrenceCategoryValue](#OccurrenceCategoryValue) : https://inspire.ec.europa.eu/codelist/OccurrenceCategoryValue

* [PopulationTypeValue](#PopulationTypeValue) : https://inspire.ec.europa.eu/codelist/PopulationTypeValue

* [ResidencyStatusValue](#ResidencyStatusValue) : https://inspire.ec.europa.eu/codelist/ResidencyStatusValue

**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 6 (3)

**Test type**: Automated

**Notes**

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
brokenLink <a name="brokenLink"/>  |  XML document '$filename', $featureType '$gmlid': The property '$propertyName' has a value '$value' that cannot be retrieved using HTTP. Every code list value must be made available in an online registry. 

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression      |Multiplicity   |Voidable
---------------------------------------------------------- | -----------------------|---------------|---------------------------------
GeneralCountingUnitValue <a name ="GeneralCountingUnitValue"></a>	| //schema-element(sd:SpeciesDistributionUnit)//sd:distributionInfo/sd:DistributionInfoType/sd:populationSize/sd:PopulationSizeType/sd:countingUnit/@xlink:href | 1 (The parent is optional) | No
Article17CountingUnitValue <a name ="Article17CountingUnitValue"></a>	| //schema-element(sd:SpeciesDistributionUnit)//sd:distributionInfo/sd:DistributionInfoType/sd:populationSize/sd:PopulationSizeType/sd:countingUnit/@xlink:href | 1 (The parent is optional) | No
TO BE COMPLETED