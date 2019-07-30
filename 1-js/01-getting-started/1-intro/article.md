
# JavaScript පිළිබඳව හැඳින්වීමක්

අපි JavaScript හි ඇති විශේෂත්වය කුමක්ද, එය සමඟ අපට අත් කරගත හැකි දේ කුමක්ද සහ  එය සමඟ හොඳින් ක්‍රියා කරන වෙනත් තාක්ෂණයන් මොනවාද යන්න සොයා බලමු .

 ## JavaScript යනු කුමක්ද?

*JavaScript* මුලින් නිර්මාණය කරන ලද්දේ  *“වෙබ් පිටු සජීවී කිරීමට”* යන තේමාවෙන්ය.

මෙම භාෂාවේ වැඩසටහන් *scripts* ලෙස හැඳින්වේ. ඒවා HTML වෙබ් පිටුවක ලිවිය හැකි අතර පිටුව load  වනවිට ස්වයංක්‍රීයව run වේ.

මෙම වැඩසටහන් code කරනු ලබන්නේ  සහ execute වෙනු ලබන්නේ plain text ලෙසය. Run  කිරීමට  විශේෂ සූදානමක් හෝ compile කිරීමක්  අවශ්‍ය නොවේ.

මේ අනුව බලන කල  JavaScript භාෂාව [Java](%28https://en.wikipedia.org/wiki/Java_%20%28program_language%29%29)  යනුවෙන් හැඳින්වෙන භාෂාවට  වඩා බෙහෙවින් වෙනස්ය.

    JavaScript  නිර්මාණය කරන විට එයට මුලින් "LiveScript" යනුවෙන්  තවත් නමක් තිබුණි. නමුත් Java  එකල ඉතා ජනප්‍රිය වූ බැවින් මෙම නව භාෂාව Java  භාෂාවේ "බාල සහෝදරයෙකු" ලෙස ස්ථානගත කිරීම උපකාරී වනු ඇතැයි තීරණය විය.
        
    නමුත් එය පරිණාමය වන විට, ජාවාස්ක්‍රිප්ට් [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) නමින් හැඳින්වෙන සම්පූර්ණ ස්වාධීන භාෂාවක් බවට පත් වූ අතර දැන් එයට Java  සමඟ කිසිදු සම්බන්ධයක් නොමැත.


අද වන විට JavaScript  බ්‍රව්සර වල පමණක් නොව, Servers වල වුවද, ඇත්ත වශයෙන්ම [JavaScript Engine](https://en.wikipedia.org/wiki/JavaScript_engine)  නමින් හැදින්වෙන විශේෂ වැඩසටහනක් ඇති ඕනෑම උපාංගයක run  කළ හැකිය.

බ්‍රව්සරවල  කාවැද්දූ එන්ජිමක් ඇත, සමහර විට එය "JavaScript virtual machine" ලෙස හැඳින්වේ.

විවිධ එන්ජින්වල විවිධ "කේත නාම" ඇත. උදාහරණයක් වශයෙන්:

 - [V8](https://en.wikipedia.org/wiki/V8_%20%28JavaScript_engine%29)  -  Chrome  සහ Opera වල.
 - [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) - Firefox වල.
 - ... IE හි විවිධ සංස්කරණ සඳහා "Trident" සහ  "Chakra", Microsoft Edge
   සඳහා,  "ChakraCore", Safari සඳහා "Nitro" සහ "SquirrelFish" වැනි වෙනත්
   කේත නාම තිබේ.

ඉහත යෙදුම් අන්තර්ජාලයේ developer articles  වල භාවිතා වන බැවින්  මතක තබා ගැනීම හොඳය. අපිද  ඒවා පාවිච්චි කරමු. උදාහරණයක් ලෙස, X නම් විශේෂාංගයක් V8 මඟින් සහය දක්වයි යනුවෙන් තිබේනම් නම්, එය බොහෝ විට Chrome  සහ Opera වල ක්‍රියා කරයි.

    එන්ජින් සංකීර්ණයි. නමුත් මූලික කරුණු පහසුය.
    
    1. එන්ජිම (එය බ්‍රව්සරයක් නම් කාවැදී ඇත) scripts කියවයි ("parses").
    2. ඉන්පසු එය scripts යන්ත්‍ර භාෂාවට පරිවර්තනය කරයි ("compile").
    3. ඉන්පසු යන්ත්‍ර කේතය ඉතා වේගයෙන් run වේ.
    
    මෙම ක්‍රියාවලියේ සෑම පියවරකදීම එන්ජිම විසින්  කේතය Optimize කරනු ලබයි. එය compile  කරන ලද script එක run වන විට පවා ඒවා නරඹා, එය හරහා ගලා යන දත්ත විශ්ලේෂණය කර, එම දැනුම මත පදනම්ව යන්ත්‍ර කේතය Optimize කරනු ලබයි. අවසානයේ script එක ඉතා වේගයෙන් run වේ.


## බ්‍රව්සරයේ run වන JavaScrpt වැඩසටහනකටකුමක් කළ හැකිද?

නූතන JavaScript  යනු “safe ” ක්‍රමලේඛන භාෂාවකි. එය මුලින් නිර්මාණය කරන ලද්දේ බ්‍රව්සර සඳහා සහ ඒ සඳහා  memory  හෝ CPU වලට low-level ප්‍රවේශයක් අවශ්‍ය නොවන බැවින් එසේ සපයන්නේ නැත. 

JavaScript හි හැකියාවන් එය ක්‍රියාත්මක වන environment එක  මත බොහෝ සෙයින් රඳා පවතී. උදාහරණයක් ලෙස, ලිපිගොනු  කියවීමට / ලිවීමට, ජාල ඉල්ලීම් ඉටු කිරීමට  Node.js සහාය දක්වයි.

බ්‍රව්සරයේ run  වෙන JavaScript වැඩසටහනකට  වෙබ් පිටු හැසිරවීම, පරිශීලකයා සමඟ අන්තර්ක්‍රියා කිරීම සහ වෙබ් සේවාදායකය (web server) සම්බන්ධ සෑම දෙයක්ම කළ හැකිය.

උදාහරණයක් ලෙස බ්‍රව්සරයේ run  වෙන JavaScript වැඩසටහනකට:

- පිටුවට නව HTML එක් කිරීම, පවතින අන්තර්ගතය වෙනස් කිරීම, styles  වෙනස් කිරීම කලහැක.
- පරිශීලක ක්‍රියාවන්ට ප්‍රතික්‍රියා කිරීම, මූසික ක්ලික් කිරීම, දර්ශක චලනයන්, යතුරු එබීම් මත ධාවනය කිරීම කලහැක .
- දුරස්ථ සේවාදායකයන් වෙත ජාලය හරහා ඉල්ලීම් යැවීම් , ගොනු බාගත කිරීම  උඩුගත කිරීම  ( [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) සහ [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) තාක්ෂණයන්).
- cookies ලබාගෙන සැකසීම, නරඹන්නාගෙන් ප්‍රශ්නඇසීම, පණිවිඩ පෙන්වීම කල හැක.
- සේවාදායකයාගේ පැත්තේ ඇති දත්ත මතක තබා ගැනීම කලහැක  ("local storage").

## බ්‍රව්සරයේ run වන JavaScrpt වැඩසටහනකට කුමක් කළ නොහැකිද?

පරිශීලකයාගේ ආරක්ෂාව සඳහා බ්‍රව්සරයේ run  වන JavaScrpt වැඩසටහනක හැකියාවන් සීමිතය. නපුරු වෙබ් පිටුවක් පුද්ගලික තොරතුරු වෙත ප්‍රවේශ වීම හෝ පරිශීලකයාගේ දත්ත වලට හානි කිරීම වැළැක්වීම මෙහි අරමුණයි.

එවැනි සීමාවන්ට උදාහරණ ලෙස:

- වෙබ් පිටුවකට දෘඩ තැටියේ අත්තනෝමතික ලිපිගොනු කියවීම / ලිවීම, ඒවා පිටපත් කිරීම හෝ වැඩසටහන් ක්‍රියාත්මක කිරීම නොකළ හැකිය. එයට OS පද්ධති ක්‍රියාකාරිත්වයට access නොමැත.

    නවීන බ්‍රව්සර් එයට ලිපිගොනු සමඟ වැඩ කිරීමට ඉඩ දෙයි, නමුත් ප්‍රවේශය සීමිත වන අතර පරිශීලකයා බ්‍රවුසර කවුළුවකට ගොනුවක් "අතහැර දැමීම" හෝ `<input>` ටැගයක් හරහා තෝරා ගැනීම වැනි යම් යම් ක්‍රියා සිදු කරන්නේ නම් පමණි.

    කැමරාව / මයික්‍රොෆෝනය සහ වෙනත් උපාංග සමඟ අන්තර් ක්‍රියා කිරීමට ක්‍රම තිබේ, නමුත් ඒවාට පරිශීලකයාගේ පැහැදිලි අවසරය අවශ්‍ය වේ. එබැවින්JavaScript  සක්‍රීය කළ පිටුවක් වෙබ් කැමරාවක් හොර රහසේ සක්‍රිය කිරීමට, වටපිටාව නිරීක්ෂණය කිරීමට සහ තොරතුරු [NSA](https://en.wikipedia.org/wiki/National_Security_Agency) වෙත යැවිය නොහැක.
    
- විවිධ ටැබ් / කවුළු සාමාන්‍යයෙන් එකිනෙකා ගැන නොදනී. සමහර විට ඒවා සිදු වේ, උදාහරණයක් ලෙස එක් කවුළුවක් අනෙක් කවුළුව විවෘත කිරීමට ජාවාස්ක්‍රිප්ට් භාවිතා කරන විට. නමුත් මෙම අවස්ථාවෙහිදී පවා, එක් පිටුවක ඇති ජාවාස්ක්‍රිප්ට් විවිධ වෙබ් අඩවි වලින් (වෙනත් domain එකක්  ,protocol එකක්  හෝ port එකක් හරහා ) පැමිණෙන්නේ නම් අනෙක් පිටුවට පිවිසිය නොහැක.

    මෙය "Same Origin Policy" ලෙස හැඳින්වේ. එසේ  වැඩ කිරීමට, පිටු දෙකම දත්ත හුවමාරුව සඳහා එකඟ විය යුතු අතර එය හසුරුවන විශේෂJavaScript  කේතයක් අඩංගු විය යුතුය. අපි එය නිබන්ධනයෙන් ආවරණය කරමු.
    
    මෙම සීමාව නැවතත්, පරිශීලකයාගේ ආරක්ෂාව සඳහා වේ. පරිශීලකයෙකු විවෘත කර ඇති http://anysite.com හි පිටුවකට http://gmail.com URL සමඟ වෙනත් බ්‍රව්සර්ටැබ් එකකට ප්‍රවේශ විය නොහැකි අතර එතැන් සිට තොරතුරු සොරකම් කළ නොහැකි විය යුතුය.

 - JavaScript වැඩසටහනට වර්තමාන පිටුව පැමිණි සේවාදායකයට  පහසුවෙන් ජාලය හරහා සන්නිවේදනය කළ හැකිය. නමුත් වෙනත් අඩවි / වසම් වලින් දත්ත ලබා ගැනීමේ   හැකියාව අඩපණ වී ඇත. හැකි වුවද, දුරස්ථ පැත්තෙන් පැහැදිලි එකඟතාවයක්   (HTTP Headers  වලින් ප්‍රකාශිත) අවශ්‍ය වේ. නැවත වරක්, එය ආරක්ෂිත  සීමාවකි.


![](limitations.svg)

Such limits do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugin/extensions which may ask for extended permissions.

## What makes JavaScript unique?

There are at least *three* great things about JavaScript:

```compare
+ Full integration with HTML/CSS.
+ Simple things are done simply.
+ Support by all major browsers and enabled by default.
```
JavaScript is the only browser technology that combines these three things.

That's what makes JavaScript unique. That's why it's the most widespread tool for creating browser interfaces.

That said, JavaScript also allows to create servers, mobile applications, etc.

## Languages "over" JavaScript

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and auto-converting it "under the hood".

Examples of such languages:

- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](http://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.

There are more. Of course, even if we use one of transpiled languages, we should also know JavaScript to really understand what we're doing.

## Summary

- JavaScript was initially created as a browser-only language, but is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language with full integration with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
