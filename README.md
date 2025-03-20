# PSAdaptiveCards
Set of classes to build AdaptiveCard object


## Example

#Build AdaptiveCard

	$AdaptiveCard = New-AdaptiveCard
	$AdaptiveCard.body += New-ColumnSet -Column 2
	$AdaptiveCard.body[0].columns[0].items = New-Image -ImageUrl $ImageUrl
	$AdaptiveCard.body[0].columns[1].width = "stretch"
	$AdaptiveCard.body[0].columns[1].items += New-TextBlock -Properties @{text="$Tenant";weight="Bolder"}
	$AdaptiveCard.body[0].columns[1].items += New-TextBlock -Text $Subject

	$AdaptiveCard.body += New-TextBlock -Text $Message

	if($Facts)
	{
		$AdaptiveCard.body += New-Fact -Facts $Facts
	}
