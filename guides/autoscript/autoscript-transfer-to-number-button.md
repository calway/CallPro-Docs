# Verbind een outbound gesprek door naar een tweede lijn via een button
Bij sommige projecten is het handig omde prospect direct naar de opdrahctgever te kunnen doorzetten. Met dit stukje code kan een button in het script worden geplaatst die het actieve gesprek direct doorverbind met het opgegeven nummer.

```javascript
<div data-role="group" data-group-type="one-state">
<button id="btnTransferSales"   type="button" class="button success outline rounded" onclick="CallTransferToNumber('0507070724')">Doorschakelen naar Sales</button>
<button id="btnTransferSupport" type="button" class="button success outline rounded" onclick="CallTransferToNumber('0507070728')">Doorschakelen naar Support</button>
</div>
<br/><br/>
<script>
function CallTransferToNumber(toTelNr) {
	if (toTelNr != "") {
		if (window.external != null) {
			var loScriptAction = window.external.GetScriptAction();
			var loScriptParams = loScriptAction.CreateParams();
			var lcCommand = "SCRIPT_TRANSFER";
			loScriptParams.Add("TYPE", "BLIND");
			loScriptParams.Add("CONTEXT", "dialer-transfer");
			loScriptParams.Add("TARGET", toTelNr);
			var llResult = loScriptAction.ExecCommand(lcCommand, loScriptParams);
		}
	}
}
</script>
```

Plaats die als een HTML veld in het script op de plaats waar de button moet komen.
