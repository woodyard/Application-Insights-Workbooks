## View Designer Vertical - json

To replicate the View Designer Vertical Workbook, copy and paste the following code into the Advanced editor, denoted by the </> symbol in toolbar

![Avanced Editor Toolbar](./ToolBar.png)

Users may have to update their query settings and subscriptions to their own accessible resources

[Return to Conversion Options](../ConversionOptions.md)

```
{
  "version": "Notebook/1.0",
  "items": [
    {
      "type": 9,
      "content": {
        "version": "KqlParameterItem/1.0",
        "crossComponentResources": [
          "/subscriptions/1f3fa6d2-851c-4a91-9087-1a050f3a9c38/resourcegroups/defaultresourcegroup-eus/providers/microsoft.operationalinsights/workspaces/defaultworkspace-1f3fa6d2-851c-4a91-9087-1a050f3a9c38-eus"
        ],
        "parameters": [
          {
            "id": "f90c348b-4933-4b02-8959-1246d4ceb19c",
            "version": "KqlParameterItem/1.0",
            "name": "Subscription",
            "type": 6,
            "isRequired": true,
            "value": "/subscriptions/5c038d14-3833-463f-a492-de956f63f12a",
            "typeSettings": {
              "additionalResourceOptions": [
                "value::1"
              ],
              "includeAll": false
            }
          },
          {
            "id": "98860972-bc1f-4305-b15e-7c529c8def06",
            "version": "KqlParameterItem/1.0",
            "name": "TimeRange",
            "type": 4,
            "isRequired": true,
            "value": {
              "durationMs": 86400000
            },
            "typeSettings": {
              "selectableValues": [
                {
                  "durationMs": 300000
                },
                {
                  "durationMs": 900000
                },
                {
                  "durationMs": 1800000
                },
                {
                  "durationMs": 3600000
                },
                {
                  "durationMs": 14400000
                },
                {
                  "durationMs": 43200000
                },
                {
                  "durationMs": 86400000
                },
                {
                  "durationMs": 172800000
                },
                {
                  "durationMs": 259200000
                },
                {
                  "durationMs": 604800000
                },
                {
                  "durationMs": 1209600000
                },
                {
                  "durationMs": 2419200000
                },
                {
                  "durationMs": 2592000000
                },
                {
                  "durationMs": 5184000000
                },
                {
                  "durationMs": 7776000000
                }
              ]
            }
          }
        ],
        "style": "pills",
        "queryType": 0,
        "resourceType": "microsoft.operationalinsights/workspaces"
      },
      "name": "parameters - 5"
    },
    {
      "type": 3,
      "content": {
        "version": "KqlItem/1.0",
        "query": "search *\r\n| where TimeGenerated {TimeRange}\r\n | summarize AggregatedValue = count() by Type | order by AggregatedValue desc\r\n| render piechart ",
        "size": 1,
        "showAnalytics": true,
        "title": "Data Type Distribution",
        "exportToExcelOptions": "visible",
        "queryType": 0,
        "resourceType": "microsoft.operationalinsights/workspaces",
        "crossComponentResources": [
          "/subscriptions/5c038d14-3833-463f-a492-de956f63f12a/resourceGroups/Aul-RG/providers/Microsoft.OperationalInsights/workspaces/AUL-Test"
        ]
      },
      "customWidth": "50",
      "showPin": true,
      "name": "query - 0",
      "styleSettings": {
        "showBorder": true
      }
    },
    {
      "type": 3,
      "content": {
        "version": "KqlItem/1.0",
        "query": "search * | summarize Count = count() by Type",
        "size": 1,
        "showAnalytics": true,
        "timeContext": {
          "durationMs": 0
        },
        "timeContextFromParameter": "TimeRange",
        "exportToExcelOptions": "visible",
        "queryType": 0,
        "resourceType": "microsoft.operationalinsights/workspaces",
        "crossComponentResources": [
          "/subscriptions/5c038d14-3833-463f-a492-de956f63f12a/resourceGroups/Aul-RG/providers/Microsoft.OperationalInsights/workspaces/AUL-Test"
        ],
        "gridSettings": {
          "formatters": [
            {
              "columnMatch": "Type",
              "formatter": 0,
              "formatOptions": {
                "showIcon": true
              }
            },
            {
              "columnMatch": "Count",
              "formatter": 4,
              "formatOptions": {
                "showIcon": true,
                "aggregation": "Count"
              },
              "numberFormat": {
                "unit": 17,
                "options": {
                  "style": "decimal"
                }
              }
            }
          ],
          "labelSettings": [
            {
              "columnId": "Type",
              "label": "Type"
            },
            {
              "columnId": "Count",
              "label": "Count"
            }
          ]
        }
      },
      "customWidth": "50",
      "name": "query - 1",
      "styleSettings": {
        "showBorder": true
      }
    },
    {
      "type": 3,
      "content": {
        "version": "KqlItem/1.0",
        "query": "search *\r\n| summarize AggregatedValue = count() by Type, bin(TimeGenerated, 1h)\r\n| sort by TimeGenerated desc\r\n| render linechart\r\n",
        "size": 1,
        "showAnalytics": true,
        "title": "Data Types Over Time",
        "timeContext": {
          "durationMs": 0
        },
        "timeContextFromParameter": "TimeRange",
        "exportToExcelOptions": "visible",
        "queryType": 0,
        "resourceType": "microsoft.operationalinsights/workspaces",
        "crossComponentResources": [
          "/subscriptions/5c038d14-3833-463f-a492-de956f63f12a/resourceGroups/Aul-RG/providers/Microsoft.OperationalInsights/workspaces/AUL-Test"
        ]
      },
      "customWidth": "50",
      "showPin": true,
      "name": "query - 2",
      "styleSettings": {
        "showBorder": true
      }
    },
    {
      "type": 3,
      "content": {
        "version": "KqlItem/1.0",
        "query": "search * | summarize Count = count() by Type",
        "size": 1,
        "showAnalytics": true,
        "timeContext": {
          "durationMs": 0
        },
        "timeContextFromParameter": "TimeRange",
        "exportToExcelOptions": "visible",
        "queryType": 0,
        "resourceType": "microsoft.operationalinsights/workspaces",
        "crossComponentResources": [
          "/subscriptions/5c038d14-3833-463f-a492-de956f63f12a/resourceGroups/Aul-RG/providers/Microsoft.OperationalInsights/workspaces/AUL-Test"
        ],
        "gridSettings": {
          "formatters": [
            {
              "columnMatch": "Type",
              "formatter": 0,
              "formatOptions": {
                "showIcon": true
              }
            },
            {
              "columnMatch": "Count",
              "formatter": 4,
              "formatOptions": {
                "showIcon": true
              },
              "numberFormat": {
                "unit": 17,
                "options": {
                  "style": "decimal"
                }
              }
            }
          ],
          "labelSettings": [
            {
              "columnId": "Type",
              "label": "Type"
            },
            {
              "columnId": "Count",
              "label": "Count"
            }
          ]
        }
      },
      "customWidth": "50",
      "name": "query - 3",
      "styleSettings": {
        "showBorder": true
      }
    },
    {
      "type": 3,
      "content": {
        "version": "KqlItem/1.0",
        "query": "search *\r\n| summarize AggregatedValue = count() by Computer | summarize Count = count()",
        "size": 1,
        "showAnalytics": true,
        "title": "Computers sending data",
        "timeContext": {
          "durationMs": 0
        },
        "timeContextFromParameter": "TimeRange",
        "exportToExcelOptions": "visible",
        "queryType": 0,
        "resourceType": "microsoft.operationalinsights/workspaces",
        "crossComponentResources": [
          "/subscriptions/5c038d14-3833-463f-a492-de956f63f12a/resourceGroups/Aul-RG/providers/Microsoft.OperationalInsights/workspaces/AUL-Test"
        ],
        "visualization": "tiles",
        "tileSettings": {
          "titleContent": {
            "formatter": 1,
            "formatOptions": {
              "showIcon": true
            }
          },
          "leftContent": {
            "columnMatch": "Count",
            "formatter": 12,
            "formatOptions": {
              "showIcon": true
            }
          },
          "showBorder": false
        }
      },
      "customWidth": "50",
      "showPin": true,
      "name": "query - 5",
      "styleSettings": {
        "showBorder": true
      }
    }
  ],
  "defaultResourceIds": [
    "/subscriptions/1f3fa6d2-851c-4a91-9087-1a050f3a9c38/resourcegroups/defaultresourcegroup-eus/providers/microsoft.operationalinsights/workspaces/defaultworkspace-1f3fa6d2-851c-4a91-9087-1a050f3a9c38-eus",
    "/subscriptions/1f3fa6d2-851c-4a91-9087-1a050f3a9c38/resourcegroups/defaultresourcegroup-eus/providers/microsoft.operationalinsights/workspaces/defaultworkspace-1f3fa6d2-851c-4a91-9087-1a050f3a9c38-eus"
  ],
  "fallbackResourceIds": [
    "/subscriptions/1f3fa6d2-851c-4a91-9087-1a050f3a9c38/resourcegroups/defaultresourcegroup-eus/providers/microsoft.operationalinsights/workspaces/defaultworkspace-1f3fa6d2-851c-4a91-9087-1a050f3a9c38-eus",
    "/subscriptions/1f3fa6d2-851c-4a91-9087-1a050f3a9c38/resourcegroups/defaultresourcegroup-eus/providers/microsoft.operationalinsights/workspaces/defaultworkspace-1f3fa6d2-851c-4a91-9087-1a050f3a9c38-eus"
  ],
  "styleSettings": {},
  "$schema": "https://github.com/woodyard/Application-Insights-Workbooks/blob/master/schema/workbook.json"
}
```