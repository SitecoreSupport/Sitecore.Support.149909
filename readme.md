# Sitecore.Support.149909
The following exception is thrown in Azure Web App environment, if you try to index content of media item. 

```
ERROR Could not compute value for ComputedIndexField: _content for indexable: sitecore://master/{8EEE161B-F7D1-4339-AE77-1FA10B8CF8D2}?lang=en&ver=1
Exception: System.Runtime.InteropServices.COMException
Message: Exception from HRESULT: 0x80048605
Source: Sitecore.ContentSearch
   at Sitecore.ContentSearch.Extracters.IFilterTextExtraction.IPersistStream.Load(IStream stream)
   at Sitecore.ContentSearch.Extracters.IFilterTextExtraction.FilterLoader.InitializeFilterAsPersistStream(IFilter filter, String fileName)
   at Sitecore.ContentSearch.Extracters.IFilterTextExtraction.FilterLoader.LoadAndInitIFilter(String fileName, String extension)
   at Sitecore.ContentSearch.Extracters.IFilterTextExtraction.FilterReader..ctor(String fileName)
   at Sitecore.ContentSearch.ComputedFields.MediaItemIFilterTextExtractor.ComputeFieldValue(IIndexable indexable)
   at Sitecore.ContentSearch.ComputedFields.MediaItemContentExtractor.ComputeFieldValue(IIndexable indexable)
   at Sitecore.ContentSearch.Azure.CloudSearchDocumentBuilder.AddComputedIndexFields()
```

Indexing of media content is based on usage of IFilters, which are not supported in Azure Web App environment. To remove this exception, it is suggested to disable media indexing by applying the current patch.


## License  
This patch is licensed under the [Sitecore Corporation A/S License for GitHub](https://github.com/sitecoresupport/Sitecore.Support.149909/blob/master/LICENSE).  

## Download  
Downloads are available via [GitHub Releases](https://github.com/sitecoresupport/Sitecore.Support.149909/releases).  

[![Github All Releases](https://img.shields.io/github/downloads/SitecoreSupport/Sitecore.Support.149909/total.svg)](https://github.com/SitecoreSupport/Sitecore.Support.149909/releases)
