# Orleans 2, Preview 3 - Bug

Trying to create custom `AuthenticationHandler` is throwing an exception in `Orleans.CodeGenerator`.

I've created this sample so it will be easily testable. 

## Prerequisites
* Git Clone
* Build Solution

## Replication Steps:
* Launch Project (F5)

## Extra Information:
* I've created `AuthHandler` which inherits from `: AuthenticationHandler<JwtBearerOptions>`.
* This is throwing an exception during runtime in `OrleansConfig.cs`  at `Line 41`.

## Exception Details:
```
Exc level 0: Orleans.CodeGenerator.CodeGenerationException: (1,3052): error CS0266: Cannot implicitly convert type 'object' to 'Microsoft.AspNetCore.Authentication.JwtBearer.JwtBearerEvents'. An explicit conversion exists (are you missing a cast?)
(1,8967): error CS0266: Cannot implicitly convert type 'object' to 'Microsoft.AspNetCore.Authentication.JwtBearer.JwtBearerEvents'. An explicit conversion exists (are you missing a cast?)
   at Orleans.CodeGenerator.CodeGeneratorCommon.CompileAssembly(GeneratedSyntax generatedSyntax, String assemblyName, Boolean emitDebugSymbols)
   at Orleans.CodeGenerator.RoslynCodeGenerator.CompileAndLoad(GeneratedSyntax generatedSyntax, Boolean emitDebugSymbols)
   at Orleans.CodeGenerator.RoslynCodeGenerator.GenerateAndLoadForAssemblies(Assembly[] inputs)	
```