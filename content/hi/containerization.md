---
title: कंटेनरीकरण
status: Completed
category: प्रौद्योगिकी
exclude_search: true
---

## यह क्या है 

कंटेनरीकरण एक एप्लीकेशन और उसकी निर्भरता को एक [कंटेनर इमेज](/hi/container-image/) में बांधने की प्रक्रिया है। कंटेनर निर्माण प्रक्रिया के लिए [ओपन कंटेनर इनिशिएटिव](https://opencontainers.org) (OCI) मानक का पालन करना आवश्यक है। जब तक आउटपुट एक कंटेनर इमेज है जो इस मानक का पालन करती है, तब तक कोई फर्क नहीं पड़ता कि किस कंटेनरीकरण उपकरण का उपयोग किया जाता है।

## समस्या  

कंटेनरों के प्रचलित होने से पहले, संगठन एक ही [बेयर-मेटल मशीन](/bare_metal_machine/) पर कई एप्लीकेशन को व्यवस्थित करने के लिए वर्चुअल मशीनों (VMs) पर निर्भर थे। VMs कंटेनरों से काफी बड़े होते हैं और उन्हें चलाने के लिए एक हाइपरवाइजर की आवश्यकता होती है। इन बड़े VM टेम्प्लेट के स्टोरेज, बैकअप और ट्रांसफर के कारण, VM टेम्पलेट्स बनाना एक धीमी प्रक्रिया है। इसके अतिरिक्त, VMs कॉन्फ़िगरेशन ड्रिफ्ट से पीड़ित हो सकते हैं जो [अपरिवर्तनीयता](/immutable_infrastructure/) के सिद्धांत का उल्लंघन करता है।

## समाधान 

पारंपरिक VM के विपरीत, कंटेनर इमेज हल्की होती हैं और कंटेनरीकरण प्रक्रिया के लिए निर्भरता की सूची वाली फ़ाइल की आवश्यकता होती है। इस फ़ाइल का संस्करण नियंत्रित किया जा सकता है और निर्माण प्रक्रिया स्वचालित हो सकती है, जिससे संगठन को अन्य प्राथमिकताओं पर ध्यान केंद्रित करने की अनुमति मिलती है जबकि स्वचालित प्रक्रियाएं निर्माण का ख्याल रखती हैं। एक कंटेनर इमेज एक अद्वितीय पहचानकर्ता द्वारा संग्रहीत की जाती है जो इसकी सटीक सामग्री और कॉन्फ़िगरेशन से जुड़ी होती है। चूंकि कंटेनरों को शेड्यूल और पुनर्निर्धारित किया जाता है, वे हमेशा अपनी प्रारंभिक स्थिति में रीसेट हो जाते हैं जो कॉन्फ़िगरेशन ड्रिफ्ट को समाप्त करता है।
