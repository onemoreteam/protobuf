``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                    Method | BytesToParse | encodedSize |         Mean |       Error |      StdDev |    Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------------------------------ |------------- |------------ |-------------:|------------:|------------:|---------:|------:|------:|----------:|
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **1** |  **51,846.9 ns** |   **467.15 ns** |   **414.12 ns** |        **-** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           1 |  47,830.1 ns |   489.54 ns |   457.91 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           1 |  45,121.9 ns |   459.91 ns |   407.69 ns |        - |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           1 |  35,535.0 ns |   495.01 ns |   463.03 ns |        - |     - |     - |         - |
|              ParseString_CodedInputStream |        10080 |           1 |  62,421.6 ns |   922.71 ns |   863.11 ns |        - |     - |     - |     168 B |
|                  ParseString_ParseContext |        10080 |           1 |  56,395.1 ns |   629.71 ns |   558.22 ns |        - |     - |     - |         - |
|               ParseBytes_CodedInputStream |        10080 |           1 | 195,003.3 ns | 3,338.68 ns | 2,959.65 ns | 135.0098 |     - |     - |  564648 B |
|                   ParseBytes_ParseContext |        10080 |           1 | 194,286.6 ns | 3,721.90 ns | 8,476.66 ns | 134.7656 |     - |     - |  564480 B |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **2** |  **31,905.1 ns** |   **614.52 ns** |   **900.76 ns** |        **-** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           2 |  28,518.9 ns |   556.18 ns |   520.25 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           2 |  30,516.6 ns |   421.93 ns |   374.03 ns |        - |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           2 |  25,817.4 ns |   421.85 ns |   373.96 ns |        - |     - |     - |         - |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **3** |  **23,663.3 ns** |   **466.84 ns** |   **573.32 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           3 |  21,847.7 ns |   290.64 ns |   257.64 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           3 |  25,370.8 ns |   308.14 ns |   288.23 ns |   0.0305 |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           3 |  24,308.7 ns |   210.15 ns |   196.58 ns |        - |     - |     - |         - |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **4** |  **20,919.8 ns** |   **394.69 ns** |   **369.19 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           4 |  20,055.8 ns |   313.40 ns |   293.15 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           4 |  23,598.5 ns |   419.07 ns |   448.40 ns |   0.0305 |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           4 |  22,993.1 ns |   307.93 ns |   257.14 ns |        - |     - |     - |         - |
|              ParseString_CodedInputStream |        10080 |           4 |  84,307.6 ns | 1,672.80 ns | 1,396.86 ns |  19.2871 |     - |     - |   80808 B |
|                  ParseString_ParseContext |        10080 |           4 |  81,533.6 ns | 1,450.09 ns | 1,611.77 ns |  19.1650 |     - |     - |   80640 B |
|               ParseBytes_CodedInputStream |        10080 |           4 |  51,954.0 ns |   929.10 ns |   869.08 ns |  38.5742 |     - |     - |  161448 B |
|                   ParseBytes_ParseContext |        10080 |           4 |  50,322.5 ns |   681.18 ns |   603.84 ns |  38.5132 |     - |     - |  161280 B |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **5** |  **19,137.8 ns** |   **149.58 ns** |   **124.90 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           5 |  19,242.9 ns |   265.12 ns |   247.99 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           5 |  22,553.2 ns |   317.09 ns |   296.61 ns |   0.0305 |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           5 |  21,885.0 ns |   426.81 ns |   419.19 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **6** |  **20,665.2 ns** |   **191.58 ns** |   **169.83 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           6 |  19,874.9 ns |   186.77 ns |   174.70 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **7** |  **20,340.3 ns** |   **336.47 ns** |   **314.74 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           7 |  20,970.6 ns |   338.51 ns |   316.65 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **8** |  **19,683.4 ns** |   **351.92 ns** |   **329.19 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           8 |  20,277.2 ns |   149.39 ns |   139.74 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **9** |  **20,667.9 ns** |   **408.87 ns** |   **401.57 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           9 |  18,903.5 ns |   236.39 ns |   221.12 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |          **10** |  **20,559.1 ns** |   **221.26 ns** |   **196.14 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |          10 |  20,262.3 ns |   334.70 ns |   313.08 ns |        - |     - |     - |         - |
|              ParseString_CodedInputStream |        10080 |          10 |  35,326.5 ns |   628.56 ns | 1,084.24 ns |   9.6436 |     - |     - |   40488 B |
|                  ParseString_ParseContext |        10080 |          10 |  34,653.2 ns |   604.05 ns |   535.47 ns |   9.5825 |     - |     - |   40320 B |
|               ParseBytes_CodedInputStream |        10080 |          10 |  20,711.1 ns |   401.33 ns |   429.42 ns |  17.3645 |     - |     - |   72744 B |
|                   ParseBytes_ParseContext |        10080 |          10 |  19,265.9 ns |   375.84 ns |   526.88 ns |  17.3340 |     - |     - |   72576 B |
|              **ParseString_CodedInputStream** |        **10080** |         **105** |   **5,436.3 ns** |   **105.47 ns** |   **140.79 ns** |   **5.3635** |     **-** |     **-** |   **22440 B** |
|                  ParseString_ParseContext |        10080 |         105 |   5,149.6 ns |    84.59 ns |    74.98 ns |   5.3253 |     - |     - |   22272 B |
| ParseString_ParseContext_MultipleSegments |        10080 |         105 |   9,576.6 ns |   165.72 ns |   155.01 ns |   5.3253 |     - |     - |   22272 B |
|               ParseBytes_CodedInputStream |        10080 |         105 |   2,520.9 ns |    41.97 ns |    37.20 ns |   3.7117 |     - |     - |   15528 B |
|                   ParseBytes_ParseContext |        10080 |         105 |   2,530.7 ns |    50.07 ns |    92.81 ns |   3.6697 |     - |     - |   15360 B |
|  ParseBytes_ParseContext_MultipleSegments |        10080 |         105 |   5,925.1 ns |   113.17 ns |   111.14 ns |   3.6697 |     - |     - |   15360 B |
|              **ParseString_CodedInputStream** |        **10080** |       **10080** |   **1,864.9 ns** |    **32.72 ns** |    **53.76 ns** |   **4.8523** |     **-** |     **-** |   **20352 B** |
|                  ParseString_ParseContext |        10080 |       10080 |   1,764.3 ns |    33.42 ns |    34.32 ns |   4.8065 |     - |     - |   20184 B |
| ParseString_ParseContext_MultipleSegments |        10080 |       10080 |   3,861.0 ns |    73.45 ns |    90.21 ns |   4.8065 |     - |     - |   20184 B |
|               ParseBytes_CodedInputStream |        10080 |       10080 |     719.0 ns |    14.34 ns |    17.07 ns |   2.4567 |     - |     - |   10304 B |
|                   ParseBytes_ParseContext |        10080 |       10080 |     687.2 ns |    13.70 ns |    30.93 ns |   2.4204 |     - |     - |   10136 B |
|  ParseBytes_ParseContext_MultipleSegments |        10080 |       10080 |   2,484.3 ns |    47.82 ns |    46.96 ns |   2.4185 |     - |     - |   10136 B |
|             **ParseFixed32_CodedInputStream** |        **10080** |           **?** |   **8,984.3 ns** |   **139.57 ns** |   **123.72 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|                 ParseFixed32_ParseContext |        10080 |           ? |   7,513.2 ns |   132.59 ns |   124.03 ns |        - |     - |     - |         - |
|             ParseFixed64_CodedInputStream |        10080 |           ? |   4,219.1 ns |    80.26 ns |    78.83 ns |   0.0381 |     - |     - |     168 B |
|                 ParseFixed64_ParseContext |        10080 |           ? |   3,596.6 ns |    31.23 ns |    29.21 ns |        - |     - |     - |         - |
|            ParseRawFloat_CodedInputStream |        10080 |           ? |   9,792.8 ns |   192.33 ns |   197.51 ns |   0.0305 |     - |     - |     168 B |
|                ParseRawFloat_ParseContext |        10080 |           ? |   7,577.4 ns |   146.88 ns |   174.85 ns |        - |     - |     - |         - |
|           ParseRawDouble_CodedInputStream |        10080 |           ? |   4,896.5 ns |    79.58 ns |    85.15 ns |   0.0381 |     - |     - |     168 B |
|               ParseRawDouble_ParseContext |        10080 |           ? |   3,796.4 ns |    72.89 ns |    74.86 ns |        - |     - |     - |         - |
