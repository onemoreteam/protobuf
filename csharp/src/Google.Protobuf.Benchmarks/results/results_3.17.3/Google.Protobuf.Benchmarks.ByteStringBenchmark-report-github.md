``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|     Method | PayloadSize |             Mean |           Error |            StdDev |           Median |    Gen 0 |    Gen 1 |    Gen 2 |  Allocated |
|----------- |------------ |-----------------:|----------------:|------------------:|-----------------:|---------:|---------:|---------:|-----------:|
|   **CopyFrom** |           **0** |        **52.602 ns** |       **0.6883 ns** |         **0.6438 ns** |        **52.807 ns** |   **0.0134** |        **-** |        **-** |       **56 B** |
| UnsafeWrap |           0 |         5.371 ns |       0.1387 ns |         0.1298 ns |         5.357 ns |   0.0076 |        - |        - |       32 B |
|   **CopyFrom** |        **1024** |       **119.113 ns** |       **2.4105 ns** |         **2.7760 ns** |       **119.063 ns** |   **0.2580** |        **-** |        **-** |     **1080 B** |
| UnsafeWrap |        1024 |         5.697 ns |       0.1894 ns |         0.1772 ns |         5.700 ns |   0.0076 |        - |        - |       32 B |
|   **CopyFrom** |      **131072** |     **8,282.980 ns** |     **165.2849 ns** |       **220.6506 ns** |     **8,291.450 ns** |  **41.6565** |  **41.6565** |  **41.6565** |   **131128 B** |
| UnsafeWrap |      131072 |         5.259 ns |       0.1799 ns |         0.1767 ns |         5.288 ns |   0.0076 |        - |        - |       32 B |
|   **CopyFrom** |     **1048576** |   **219,422.660 ns** |   **4,338.1539 ns** |    **11,275.4388 ns** |   **217,896.936 ns** | **206.0547** | **205.5664** | **205.5664** |  **1049565 B** |
| UnsafeWrap |     1048576 |         5.270 ns |       0.1768 ns |         0.2420 ns |         5.237 ns |   0.0076 |        - |        - |       32 B |
|   **CopyFrom** |    **10485760** | **5,251,680.938 ns** | **445,877.4327 ns** | **1,314,679.6703 ns** | **6,028,859.375 ns** | **156.2500** | **156.2500** | **156.2500** | **10485814 B** |
| UnsafeWrap |    10485760 |         5.231 ns |       0.1445 ns |         0.1206 ns |         5.232 ns |   0.0076 |        - |        - |       32 B |