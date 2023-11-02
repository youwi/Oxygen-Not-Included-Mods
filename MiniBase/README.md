

编译时:
1 修改引用dll
2 修改事件脚本
3 配置Nuget,更新2个库

# 脚本A:
mkdir  $(ONI_MOD_LOCAL)\$(ProjectName)
"$(ILMergeConsolePath)"  /out:$(TargetName)-merged.dll $(TargetName).dll PLib.dll  
copy /y $(TargetDir)$(ProjectName)*-merged*  $(ONI_MOD_LOCAL)\$(ProjectName)\
xcopy /y /s $(ProjectDir)resource\*  $(ONI_MOD_LOCAL)\$(ProjectName)\

# 脚本B:
"$(ILMergeConsolePath)" /lib:"$(SolutionDir)/PLib/" /out:$(TargetName)-merged.dll $(TargetName).dll PLib.dll /targetplatform:v4,C:/Windows/Microsoft.NET/Framework64/v4.0.30319
mkdir "%HOMEPATH%\Documents\Klei\OxygenNotIncluded\mods\dev\$(ProjectName)"

copy "$(TargetName)-merged.dll" "%HOMEPATH%\Documents\Klei\OxygenNotIncluded\mods\dev\$(ProjectName)\$(ProjectName)-merged.dll"

"$(ILMergeConsolePath)"  /out:$(TargetName)-merged.dll $(TargetName).dll PLib.dll  
xcopy /y /s $(TargetDir)\mod*  $(ONI_MOD_LOCAL)\$(ProjectName)\
xcopy /y /s $(TargetDir)\mod*  $(ONI_MOD_LOCAL)\$(ProjectName)\


"Newtonsoft.Json.dll"

# 为何要合并DLL呀? 这么久了都不记得了

# 添加了什么或删除了什么也没知道,都不记得了

# 使用Nuget来管理代码包  Plib  ilmerge 


// "Newtonsoft.Json.dll"

