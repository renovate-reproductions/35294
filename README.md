# 35294

Reproduction for [Renovate discussion 35294](https://github.com/renovatebot/renovate/discussions/35294).

## Current behavior

Renovate does not detect System.ValueTuple version update to 4.6.1.

```
DEBUG: 0 flattened updates found:  (repository=local)
DEBUG: Returning 0 branch(es) (repository=local)
DEBUG: config.repoIsOnboarded=true (repository=local)
DEBUG: packageFiles with updates (repository=local)
       "config": {
         "nuget": [
           {
             "deps": [
               {
                 "datasource": "nuget",
                 "depType": "nuget",
                 "depName": "System.ValueTuple",
                 "currentValue": "4.6.0",
                 "updates": [],
                 "packageName": "System.ValueTuple",
                 "versioning": "nuget",
                 "warnings": [],
                 "sourceUrl": "https://github.com/dotnet/maintenance-packages",
                 "registryUrl": "https://api.nuget.org/v3/index.json",
                 "currentVersion": "4.6.1",
                 "currentVersionTimestamp": "2025-03-19T23:28:30.970Z",
                 "currentVersionAgeInDays": 20
               }
             ],
             "packageFile": "Packages.props"
           }
         ]
       }
```

## Expected behavior

Update should be detected. Log from last working version 38.34.0

```
DEBUG: 1 flattened updates found: System.ValueTuple (repository=local)
DEBUG: Returning 1 branch(es) (repository=local)
DEBUG: config.repoIsOnboarded=true (repository=local)
DEBUG: packageFiles with updates (repository=local)
       "config": {
         "nuget": [
           {
             "deps": [
               {
                 "datasource": "nuget",
                 "depType": "nuget",
                 "depName": "System.ValueTuple",
                 "currentValue": "4.6.0",
                 "updates": [
                   {
                     "bucket": "non-major",
                     "newVersion": "4.6.1",
                     "newValue": "4.6.1",
                     "releaseTimestamp": "2025-03-19T23:28:30.970Z",
                     "newMajor": 4,
                     "newMinor": 6,
                     "newPatch": 1,
                     "updateType": "patch",
                     "branchName": "renovate/system.valuetuple-4.x"
                   }
                 ],
                 "packageName": "System.ValueTuple",
                 "versioning": "nuget",
                 "warnings": [],
                 "sourceUrl": "https://github.com/dotnet/maintenance-packages",
                 "registryUrl": "https://api.nuget.org/v3/index.json",
                 "currentVersion": "4.6.0",
                 "currentVersionTimestamp": "1900-01-01T00:00:00.000Z",
                 "isSingleVersion": true,
                 "fixedVersion": "4.6.0"
               }
             ],
             "packageFile": "Packages.props"
           }
         ]
       }
```

