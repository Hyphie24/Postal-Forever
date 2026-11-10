# Postal Community Edition

## [v4.4.3](https://github.com/paradosi/postal-community-edition/tree/v4.4.3) (2026-09-02)
[Full Changelog](https://github.com/paradosi/postal-community-edition/compare/v4.4.2...v4.4.3) [Previous Releases](https://github.com/paradosi/postal-community-edition/releases)

- v4.4.3: Fix BlackBook alt-menu scoping, restore Wago publishing  
    - Your own character appeared in the paginated all-realms alt menu.  
      BlackBook.lua declares plre (player-realm) inside the allalt branch  
      but read it in aapart and sapart, where it is out of scope and so  
      nil, making the guard `pr ~= plre` always true. Only visible with  
      more than 25 alts, when those paginated submenus appear. The  
      same-realm list was unaffected in practice, since altstable is built  
      with the current character already excluded.  
    - Removed an undefined-global read in delsapart: `p = all and  
      p.."-"..r or p` referenced an `all` not in scope there. It behaved  
      correctly by accident -- same-realm lists are never realm-qualified,  
      and the nil read evaluated as false would -- but it would break if  
      any other addon defined a global named `all`.  
    Packaging:  
    - X-Wago-ID existed only in Postal\_TBC.toc. The BigWigs packager reads  
      metadata from the TOC matching package-as (Postal.toc), which had  
      neither a Wago nor a CurseForge id, so releases had no Wago upload  
      target. Added to all six TOC files. There is still no  
      X-Curse-Project-ID anywhere.  
    Cleanup:  
    - Removed the orphaned Express.MouseWheel default, the addon's only  
      reference to itself. Express has no mousewheel handling and the key  
      was never exposed in any menu.  
    Not verified in game.  
    Co-Authored-By: Claude Opus 5 (1M context) <noreply@anthropic.com>  
    Claude-Session: https://claude.ai/code/session\_01AWwEY7j7phYrfcxJZsQDVb  
- Merge pull request #7 from paradosi/copilot/fix-format-string-error  
- Fix nil error in BlackBook.lua by using LOCALIZED\_CLASS\_NAMES\_MALE[c] or c fallback  
    Agent-Logs-Url: https://github.com/paradosi/postal-community-edition/sessions/fb042453-1fd1-4df7-92b7-a85f725afc6a  
    Co-authored-by: paradosi <175656799+paradosi@users.noreply.github.com>  
- Initial plan  
- Merge pull request #5 from paradosi/copilot/bump-toc-version  
- Bump TOC version to 4.4.2 across all expansion TOC files  
    Co-authored-by: paradosi <175656799+paradosi@users.noreply.github.com>  
    Agent-Logs-Url: https://github.com/paradosi/postal-community-edition/sessions/ce1670a0-7d6a-4ee4-bea8-b1635890d258  
- Initial plan  
- Refresh contributors cache  
