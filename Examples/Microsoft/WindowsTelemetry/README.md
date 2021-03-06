# Windows Telemetry connectivity tests

## Usage

1. Import this file: `Import-Module .\WindowsTelemetryConnectivity.psm1`
1. Run one of the following:
    * `$connectivity = Get-WindowsTelemetryConnectivity`
    * `$connectivity = Get-WindowsTelemetryConnectivity -Verbose`
    * `$connectivity = Get-WindowsTelemetryConnectivity -PerformBlueCoatLookup`
    * `$connectivity = Get-WindowsTelemetryConnectivity -Verbose -PerformBlueCoatLookup`
1. Filter results: `$connectivity | Format-List -Property Blocked,TestUrl,UnblockUrl,DnsAliases,IpAddresses,Description,Resolved,ActualStatusCode,ExpectedStatusCode,UnexpectedStatus`
1. Save results to a file: `Save-HttpConnectivity -Objects $connectivity -FileName ('WindowsTelemetryConnectivity_{0:yyyyMMdd_HHmmss}' -f (Get-Date))`

## Tested URLs

| Test URL | URL to Unblock | Description |
| -- | -- | -- |
| <https://v10.vortex-win.data.microsoft.com/collect/v1> | <https://v10.vortex-win.data.microsoft.com> | Diagnostic/telemetry data for Windows 10 1607 and later. |
| <https://v20.vortex-win.data.microsoft.com/collect/v1> | <https://v20.vortex-win.data.microsoft.com> | Diagnostic/telemetry data for Windows 10 1703 and later. |
| <https://settings-win.data.microsoft.com> | <https://settings-win.data.microsoft.com> | Used by applications, such as Windows Connected User Experiences and Telemetry component and Windows Insider Program, to dynamically update their configuration. |
| <https://watson.telemetry.microsoft.com> | <https://watson.telemetry.microsoft.com> | Windows Error Reporting (WER). |
| <https://ceuswatcab01.blob.core.windows.net> | <https://ceuswatcab01.blob.core.windows.net> | Windows Error Reporting (WER) Central US 1. |
| <https://ceuswatcab02.blob.core.windows.net> | <https://ceuswatcab02.blob.core.windows.net> | Windows Error Reporting (WER) Central US 2. |
| <https://eaus2watcab01.blob.core.windows.net> | <https://eaus2watcab01.blob.core.windows.net> | Windows Error Reporting (WER) East US 1. |
| <https://eaus2watcab02.blob.core.windows.net | <https://eaus2watcab02.blob.core.windows.net> | Windows Error Reporting (WER) East US 2. |
| <https://weus2watcab01.blob.core.windows.net> | <https://weus2watcab01.blob.core.windows.net> | Windows Error Reporting (WER) West US 1. |
| <https://weus2watcab02.blob.core.windows.net> | <https://weus2watcab02.blob.core.windows.net> | Windows Error Reporting (WER) West US 2. |
| <https://oca.telemetry.microsoft.com> | <https://oca.telemetry.microsoft.com> | Online Crash Analysis (OCA). |
| <https://vortex.data.microsoft.com/collect/v1> | <https://vortex.data.microsoft.com> | OneDrive application for Windows 10. |

## References

* [Configure Windows diagnostic data in your organization - Endpoints](https://docs.microsoft.com/en-us/windows/privacy/configure-windows-diagnostic-data-in-your-organization#endpoints)