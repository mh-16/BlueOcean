#!/usr/bin/env groovy

node ('master')
{
    stage 'Checkout code'
        git 'https://github.com/mh-16/BlueOcean.git'
    stage 'Nuget'
       bat 'C:/Tools/nuget.exe restore SeleniumNUnitParam.sln -source "https://www.nuget.org/api/v2/"'
    stage 'Build'
        bat "\"${tool 'msbuild'}\" SeleniumNUnitParam.sln /p:Configuration=debug /p:platform=\"Any CPU\" /p:ProductVersion=1.0.0.${BUILD_NUMBER}"
    stage 'Test'
        bat '"C:/Tools/Nunit/nunit3-console.exe" "C:\Program Files (x86)\Jenkins\workspace\TestPipeline_master-4JM27EXS2RGGKJ6BGNZQZX3EOXE2VOHVSFCSQFCNP2U7GIQZ6IFQ\SeleniumNUnitParam\bin\Debug\SeleniumNUnitParam.dll"'

'
    
}