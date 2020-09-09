function WriteXmlToScreen ([xml]$xml)
{
    $StringWriter = New-Object System.IO.StringWriter;
    $XmlWriter = New-Object System.Xml.XmlTextWriter $StringWriter;
    $XmlWriter.Formatting = "indented";
    $xml.WriteTo($XmlWriter);
    $XmlWriter.Flush();
    $StringWriter.Flush();
    Write-Output $StringWriter.ToString();
}


Write-Host "---------------------------------"
Write-Host "Resharper code inspection report..." 
Write-Host "---------------------------------"
[xml]$insdoc = Get-Content -Path insreport.xml
WriteXmlToScreen $insdoc

Write-Host ""
Write-Host "---------------------------------"
Write-Host "Resharper code duplication report..." 
Write-Host "---------------------------------"
[xml]$dupdoc = Get-Content -Path dupreport.xml
WriteXmlToScreen $dupdoc

Write-Host ""
Write-Host "---------------------------------"
Write-Host "Resharper report analysis..." 
Write-Host "---------------------------------"

$issuetypes = $insdoc.SelectNodes("//IssueTypes/IssueType")

$result = 0

if($issuetypes.count -eq 0){
    Write-Host "Number of Inspection Violations:" $issuetypes.count -ForegroundColor green 
}
else{
    Write-Host "Number of Inspection Violations:" $issuetypes.count -ForegroundColor red
    $result = 1
}


$duplicateCost = $dupdoc.DuplicatesReport.Statistics.TotalDuplicatesCost

if($duplicateCost -eq 0){
    Write-Host "Cost of Duplicate Code:" $duplicateCost -ForegroundColor green 
}
else{
    Write-Host "Cost of Duplicate Code:" $duplicateCost -ForegroundColor red 
    $result = 1
}

exit $result
