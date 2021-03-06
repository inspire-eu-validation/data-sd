# Constraints

**Purpose**: Verify that the features provided in the dataset adhere to the constraints specified in the INSPIRE application schema.

**Prerequisites**

**Test method**

The following checks are performed for every feature in the dataset.

* Check that if the [geometry](#geometry) of the Species Distribution Unit feature type has no value, a reference to a [spatial object](#spatial_object) needs to be provided. (OCL: self.geometry->isEmpty() implies self.spatialObject->notEmpty())


**Reference(s)**: 

* [TG DS Template](./README.md#ref_TG_DS_tmpl) IR requirement Article 4 (2)
* [TG DS-SD](./README.md#ref_TG_DS_SD) 5.3.2.1.2

**Test type**: Automated

**Notes** 

Verify that the OCL constraints that are specified in the UML model of the application schema are met, i.e. validate features against the constraints. For unmet constraints report [constraintViolation](#constraintViolation).

## Messages

Identifier  |  Message text (parameters start with '$')
---------------------------------------------------------- | -------------------------------------------------------------------------
constraintViolation <a name="constraintViolation"/>  |  XML document '$filename', $featureType '$gmlid': The constraint '$constraint' is violated.

## Contextual XPath references

The namespace prefixes used as described in [README](./README.md#namespaces).

Abbreviation                                               |  XPath expression                     |Multiplicity       |Voidable
---------------------------------------------------------- | ------------------------------------- | ------------------|----------
geometry <a name="geometry"></a> | //schema-element(sd:SpeciesDistributionUnit)/sd:geometry|0..1 |No
spatial object <a name="spatial_object"></a> | //schema-element(sd:SpeciesDistributionUnit)/sd:spatialObject|0..1 |Yes
