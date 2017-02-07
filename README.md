# unity-setup
###*Just setup, bro!*


#Scene And Prefab Merging Setup

## Requirements
1. [Git](https://git-scm.com), ofcource
2. Install [ __Perforce P4Merge__ ](https://www.perforce.com/downloads/helix)
3. [SourceTree](https://www.sourcetreeapp.com/)
4. [Unity](https://unity3d.com) 


## Unity Setup

1.  Assets  > Project Settings > Editor :
	- Version Control > *Visible Meta Files*
	- Asset Serialization > *Force Text*

2. Change *mergespecfile.txt* (_**YourUnityFolder**\Editor\Data\Tools\mergespecfile.txt_)
	> 
	Find lines "unity use", "prefab use" and change it like below:
	>
	unity use "C:\Program Files\Perforce\p4merge.exe" "$BASE" "$REMOTE” “$LOCAL” “$MERGED”
  >
	prefab use "C:\Program Files\Perforce\p4merge.exe" "$BASE" "$REMOTE” “$LOCAL” “$MERGED”


## SourceTree Setup
###UnityYAMLMerge
1. Open _Tools > Options > Diff_
2.  Merge Tool : _Custom_
3.  Diff Command:  _**YourUnityFolder**\Editor\Data\Tools\UnityYAMLMerge.exe_
4. Arguments: _merge -p $BASE $REMOTE $LOCAL $MERGED_

###P4Merge
1. Open _Tools > Options > Diff_
2.  External Merge Tool : _P4Merge_
