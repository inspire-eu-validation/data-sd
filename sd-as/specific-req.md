# Species Distribution theme-specific requirements

**Purpose**: Verify that the features provided in the dataset adhere to the theme-specific requirements specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following checks shall be manually performed for every feature in the dataset.

* Where grid representations of species distributions are needed, the Grid_ETRS89-LAEA as defined in Section 2.2.1 of Annex II shall be used.
* For SpeciesDistributionUnit spatial objects:
	* if a species has not been actively searched for, the distributionInfo attribute shall be void with reason “unknown”,
	* and if a species has been actively searched for, but has not been found, the value of the attribute occurenceCategory of DistributionInfoType shall be “absent”."


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-SD](./README.md#ref_TG_DS_SD) 5.3.1.2; 6.2.1

**Test type**: Manual

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

