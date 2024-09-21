## Welcome to the Fortnite Modding guide! 
written by tevtongermany
this guide is specific for 24.20 UEFN PIE

so to start modding you would need following things
- Some basic Knowledge about Unreal engine such as creating BP's, Import audio files, etc
- 24.20 including UEFN Paks and Executable
- Xdelta
- Neonite
- Fiddler
To download 24.20 you would need to have legendary and the manifest for that further instruction you can find [here!](https://github.com/bc2424/UEFN-PIE) You can Ignore step 7 If you want to use Neonite you would need to download it from [here](https://github.com/HybridFNBR/Neonite) you also would need to use a modified version of the fiddler script

```c#
import System;
import System.Web;
import System.Windows.Forms;
import Fiddler;

class Handlers
{ 
    static function OnBeforeRequest(oSession: Session) {
        if (oSession.hostname.Contains("epicgames.com")) {
            if (oSession.HTTPMethodIs("CONNECT"))
            {
                oSession["x-replywithtunnel"] = "FortniteTunnel";
                return;
            }
            oSession.fullUrl = "http://localhost:5595" + oSession.PathAndQuery;
        }
        else if (oSession.hostname.Contains("epicgames.net")) {
            if (oSession.HTTPMethodIs("CONNECT"))
            {
                oSession["x-replywithtunnel"] = "FortniteTunnel";
                return;
            }
            oSession.fullUrl = "http://localhost:5595" + oSession.PathAndQuery;
        }
        else if (oSession.hostname.Contains("epicgames.dev")) {
            if (oSession.HTTPMethodIs("CONNECT"))
            {
                oSession["x-replywithtunnel"] = "FortniteTunnel";
                return;
            }
            oSession.fullUrl = "http://localhost:5595" + oSession.PathAndQuery;
        }
    }
}
```

And you are pretty much done!
I would Recommend you joining the Fortnite Modding hub since this guide will reference files and other stuff from there!
https://discord.gg/wsTdHHseGP

you can do almost everything you want in uefn pie here is some things you could try out
[[Creating Custom Skins]]
[[Creating Music Packs]]

Credits:

The Goat that even made this possible: [Boredcrow24](https://x.com/boredcrow24)
The guy who showed me how to import custom skins: Armoon
The Skin used in [[Creating Custom Skins]] made by: [Snoopy](https://x.com/Snoopity_Dog420)
