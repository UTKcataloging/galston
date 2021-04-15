# OpenRefine Template for Galston (Compound Object)

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
{{if(isBlank(cells['identifier'].value), '', '<identifier type="catalog">' + cells['identifier'].value + '</identifier>')}}
{{if(isBlank(cells['pid'].value), '', '<identifier type="pid">' + cells['pid'].value + '</identifier>')}}
{{if(isBlank(cells["title"].value), '', '<titleInfo supplied="yes"><title>' + cells["title"].value + '</title></titleInfo>')}}
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form>
{{if(isBlank(cells['form2'].value), '', '<form authority="aat" valueURI="' + cells['form2_URI'].value + '">' + cells['form2'].value + '</form>')}}
</physicalDescription>
{{if(isBlank(cells['photographer'].value), '', '<name'+ if(isBlank(cells['photographer_URI'].value), '', ' valueURI="' + cells['photographer_URI'].value + '"' + ' authority="naf"') + '><namePart>' + cells['photographer'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm></role></name>')}}
{{if(isBlank(cells['artist'].value), '', '<name'+ if(isBlank(cells['artist_URI'].value), '', ' valueURI="' + cells['artist_URI'].value + '"' + ' authority="naf"') + '><namePart>' + cells['artist'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/art">Artist</roleTerm></role></name>')}}
{{if(isBlank(cells['addressee'].value), '', '<name'+ if(isBlank(cells['addressee_URI'].value), '', ' valueURI="' + cells['addressee_URI'].value + '"' + ' authority="naf"') + '><namePart>' + cells['addressee'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/rcp">Addressee</roleTerm></role></name>')}}
{{if(isBlank(cells['correspondent'].value), '', '<name'+ if(isBlank(cells['correspondent_URI'].value), '', ' valueURI="' + cells['correspondent_URI'].value + '"' + ' authority="naf"') + '><namePart>' + cells['correspondent'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/crp">Correspondent</roleTerm></role></name>')}}
{{if(isBlank(cells['restorationist'].value), '', '<name'+ if(isBlank(cells['restorationist_URI'].value), '', ' valueURI="' + cells['restorationist_URI'].value + '"' + ' authority="naf"') + '><namePart>' + cells['restorationist'].value + '</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/rsr">Restorationist</roleTerm></role></name>')}}
<originInfo>
{{if(isBlank(cells['subject_geo_originplace'].value), '', '<place><placeTerm valueURI="' + cells['subject_geo_URI'].value + '">' + cells['subject_geo_originplace'].value + '</placeTerm></place>')}}
{{if(isBlank(cells['dateCreated'].value), '', '<dateCreated>' + cells['dateCreated'].value + '</dateCreated><dateCreated encoding="edtf">' + cells['date_edtf'].value + '</dateCreated>')}}
{{if(isBlank(cells['date_approximate'].value), '', '<dateCreated qualifier="approximate">' + cells['date_approximate'].value + '</dateCreated>' + if(isBlank(cells['date_approx_edtf'].value), '', '<dateCreated encoding="edtf" qualifier="approximate">' + cells['date_approximate'].value + '</dateCreated>') + if(isBlank(cells['date_approx_start'].value), '', '<dateCreated encoding="edtf" qualifier="approximate" point="start">' + cells['date_approx_start'].value + '</dateCreated><dateCreated encoding="edtf" qualifier="approximate" point="end">' + cells['date_approx_end'].value + '</dateCreated>'))}}
</originInfo>
{{if(isBlank(cells['subject_topic'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_topic_URI'].value + '"><topic>' + cells['subject_topic'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_topic2_URI'].value + '"><topic>' + cells['subject_topic2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_topic3_URI'].value + '"><topic>' + cells['subject_topic3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic4'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject_topic4_URI'].value + '"><topic>' + cells['subject_topic4'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_name'].value), '', '<subject' + if(isBlank(cells['subject_name_URI'].value), '', ' authority="naf" valueURI="' + cells['subject_name_URI'].value + '"') + '><name><namePart>' + cells['subject_name'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name2'].value), '', '<subject' + if(isBlank(cells['subject_name2_URI'].value), '', ' authority="naf" valueURI="' + cells['subject_name2_URI'].value + '"') + '><name><namePart>' + cells['subject_name2'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name3'].value), '', '<subject' + if(isBlank(cells['subject_name3_URI'].value), '', ' authority="naf" valueURI="' + cells['subject_name3_URI'].value + '"') + '><name><namePart>' + cells['subject_name3'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name4'].value), '', '<subject' + if(isBlank(cells['subject_name4_URI'].value), '', ' authority="naf" valueURI="' + cells['subject_name4_URI'].value + '"') + '><name><namePart>' + cells['subject_name4'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_geo_originplace'].value), '', '<subject authority="geonames" valueURI="' + cells['subject_geo_URI'].value + '"><geographic>' + cells['subject_geo_originplace'].value + '</geographic><cartographics><coordinates>' + cells['coordinates'].value + '</coordinates></cartographics></subject>')}}
<typeOfResource>{{cells['typeOfResource'].value}}</typeOfResource>
{{if(isBlank(cells['typeOfResource2'].value), '', '<typeOfResource>' + cells['typeOfResource2'].value + '</typeOfResource>')}}
{{if(isBlank(cells['language'].value), '', '<language><languageTerm authority="iso639-2b" type="text">' + cells['language'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['language2'].value), '', '<language><languageTerm authority="iso639-2b" type="term">' + cells['language2'].value + '</languageTerm></language>')}}
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Gottfried Galston Collection</title></titleInfo></relatedItem>
{{if(isBlank(cells['archival_collection'].value), '', '<relatedItem displayLabel="Collection" type="host"><titleInfo><title>' + cells['archival_collection'].value + '</title></titleInfo><identifier>' + cells['collection_identifier'].value + '</identifier></relatedItem>')}}
<location><physicalLocation valueURI="{{cells['repository_URI'].value}}">{{cells['repository'].value}}</physicalLocation></location>
<recordInfo><recordContentSource valueURI="{{cells['record_source_URI'].value}}">{{cells['record_source'].value}}</recordContentSource><languageOfCataloging>
<languageTerm type="text" authority="iso639-2b">English</languageTerm>
</languageOfCataloging></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```