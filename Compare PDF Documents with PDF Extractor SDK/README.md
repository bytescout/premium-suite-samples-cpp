## compare PDF documents with PDF extractor SDK in C++ with ByteScout Premium Suite

### Learn to code compare PDF documents with PDF extractor SDK in C++: How-To tutorial

Easy to understand coding instructions are written to assist you to try-out the features without the requirement to write your own code. ByteScout Premium Suite was created to assist compare PDF documents with PDF extractor SDK in C++. ByteScout Premium Suite is the bundle that includes twelve SDK products from ByteScout including tools and components for PDF, barcodes, spreadsheets, screen video recording.

This rich and prolific sample source code in C++ for ByteScout Premium Suite contains various functions and options you should do calling the API to implement compare PDF documents with PDF extractor SDK.  Just copy and paste this C++ sample code to your C++ application's code editor, add a reference to ByteScout Premium Suite (if you haven't added yet) and you are ready to go! Enjoy writing a code with ready-to-use sample C++ codes to implement compare PDF documents with PDF extractor SDK using ByteScout Premium Suite.

Trial version along with the source code samples for C++ can be downloaded from our website

## REQUEST FREE TECH SUPPORT

[Click here to get in touch](https://bytescout.zendesk.com/hc/en-us/requests/new?subject=ByteScout%20Premium%20Suite%20Question)

or just send email to [support@bytescout.com](mailto:support@bytescout.com?subject=ByteScout%20Premium%20Suite%20Question) 

## ON-PREMISE OFFLINE SDK 

[Get Your 60 Day Free Trial](https://bytescout.com/download/web-installer?utm_source=github-readme)
[Explore SDK Docs](https://bytescout.com/documentation/index.html?utm_source=github-readme)
[Sign Up For Online Training](https://academy.bytescout.com/)


## ON-DEMAND REST WEB API

[Get your API key](https://pdf.co/documentation/api?utm_source=github-readme)
[Explore Web API Documentation](https://pdf.co/documentation/api?utm_source=github-readme)
[Explore Web API Samples](https://github.com/bytescout/ByteScout-SDK-SourceCode/tree/master/PDF.co%20Web%20API)

## VIDEO REVIEW

[https://www.youtube.com/watch?v=NEwNs2b9YN8](https://www.youtube.com/watch?v=NEwNs2b9YN8)




<!-- code block begin -->

##### ****CPPExample.cpp:**
    
```
	#include "stdafx.h"
	#include "comip.h"

	#import "c:\\Program Files\\Bytescout PDF Extractor SDK\\net4.00\\Bytescout.PDFExtractor.tlb" raw_interfaces_only
	
	using namespace Bytescout_PDFExtractor;

	int _tmain(int argc, _TCHAR* argv[])
	{
		// Initialize COM.
		HRESULT hr = CoInitializeEx(NULL, COINIT_APARTMENTTHREADED);

		// Load first document
		_TextExtractorPtr document1(__uuidof(TextExtractor));
		document1->put_RegistrationName(_bstr_t(L"DEMO"));
		document1->put_RegistrationKey(_bstr_t(L"DEMO"));
		document1->LoadDocumentFromFile(_bstr_t(L"..\\..\\comparison1.pdf"));

		// Load second  document
		_TextExtractorPtr document2(__uuidof(TextExtractor));
		document2->put_RegistrationName(_bstr_t(L"DEMO"));
		document2->put_RegistrationKey(_bstr_t(L"DEMO"));
		document2->LoadDocumentFromFile(_bstr_t(L"..\\..\\comparison2.pdf"));

		// Compare documents
		_TextComparerPtr comparer(__uuidof(TextComparer));
		comparer->put_RegistrationName(_bstr_t(L"DEMO"));
		comparer->put_RegistrationKey(_bstr_t(L"DEMO"));
		DECIMAL result;
		comparer->Compare((_BaseTextExtractorPtr) document1, (_BaseTextExtractorPtr) document2, &result);

		// Generate report
		VARIANT_BOOL ok;
		comparer->GenerateHtmlReport_2(_bstr_t(L"report.html"), &ok);

		document1->Release();
		document2->Release();
		comparer->Release();

		CoUninitialize();

		return 0;
	}


```

<!-- code block end -->    

<!-- code block begin -->

##### ****stdafx.cpp:**
    
```
// stdafx.cpp : source file that includes just the standard includes
// CPPExample.pch will be the pre-compiled header
// stdafx.obj will contain the pre-compiled type information

#include "stdafx.h"

// TODO: reference any additional headers you need in STDAFX.H
// and not in this file

```

<!-- code block end -->    

<!-- code block begin -->

##### ****stdafx.h:**
    
```
// stdafx.h : include file for standard system include files,
// or project specific include files that are used frequently, but
// are changed infrequently
//

#pragma once

#include "targetver.h"

#include <stdio.h>
#include <tchar.h>



// TODO: reference additional headers your program requires here

```

<!-- code block end -->    

<!-- code block begin -->

##### ****targetver.h:**
    
```
#pragma once

// Including SDKDDKVer.h defines the highest available Windows platform.

// If you wish to build your application for a previous Windows platform, include WinSDKVer.h and
// set the _WIN32_WINNT macro to the platform you wish to support before including SDKDDKVer.h.

#include <SDKDDKVer.h>

```

<!-- code block end -->