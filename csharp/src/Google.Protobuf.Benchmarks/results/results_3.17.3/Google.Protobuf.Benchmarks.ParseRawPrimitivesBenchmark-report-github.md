``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                    Method | BytesToParse | encodedSize |         Mean |       Error |      StdDev |    Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------------------------------ |------------- |------------ |-------------:|------------:|------------:|---------:|------:|------:|----------:|
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **1** |  **51,134.3 ns** |   **993.33 ns** |   **829.48 ns** |        **-** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           1 |  41,792.2 ns |   480.41 ns |   425.88 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           1 |  48,160.0 ns |   532.84 ns |   498.42 ns |        - |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           1 |  36,157.3 ns |   719.24 ns |   769.58 ns |        - |     - |     - |         - |
|              ParseString_CodedInputStream |        10080 |           1 |  66,788.2 ns |   680.12 ns |   602.91 ns |        - |     - |     - |     168 B |
|                  ParseString_ParseContext |        10080 |           1 |  62,072.7 ns | 1,178.87 ns | 1,210.61 ns |        - |     - |     - |         - |
|               ParseBytes_CodedInputStream |        10080 |           1 | 198,209.2 ns | 1,552.24 ns | 1,376.02 ns | 135.0098 |     - |     - |  564648 B |
|                   ParseBytes_ParseContext |        10080 |           1 | 200,448.6 ns | 3,565.51 ns | 3,335.18 ns | 134.7656 |     - |     - |  564480 B |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **2** |  **30,437.5 ns** |   **460.66 ns** |   **408.36 ns** |        **-** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           2 |  25,531.9 ns |   378.75 ns |   335.75 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           2 |  32,725.4 ns |   321.23 ns |   284.76 ns |        - |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           2 |  25,566.4 ns |   303.04 ns |   283.47 ns |        - |     - |     - |         - |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **3** |  **23,421.1 ns** |   **323.89 ns** |   **270.46 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           3 |  21,406.3 ns |   417.82 ns |   410.36 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           3 |  25,507.6 ns |   288.82 ns |   256.03 ns |   0.0305 |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           3 |  22,893.7 ns |   315.43 ns |   295.06 ns |        - |     - |     - |         - |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **4** |  **20,338.1 ns** |   **305.10 ns** |   **285.39 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           4 |  19,952.3 ns |   328.81 ns |   291.48 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           4 |  23,376.7 ns |   337.11 ns |   315.33 ns |   0.0305 |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           4 |  21,904.3 ns |   430.74 ns |   381.84 ns |        - |     - |     - |         - |
|              ParseString_CodedInputStream |        10080 |           4 |  84,269.6 ns |   902.04 ns |   799.64 ns |  19.2871 |     - |     - |   80808 B |
|                  ParseString_ParseContext |        10080 |           4 |  82,893.6 ns | 1,607.73 ns | 1,503.87 ns |  19.1650 |     - |     - |   80640 B |
|               ParseBytes_CodedInputStream |        10080 |           4 |  52,005.6 ns | 1,039.92 ns |   972.74 ns |  38.5742 |     - |     - |  161448 B |
|                   ParseBytes_ParseContext |        10080 |           4 |  51,525.9 ns |   740.47 ns |   656.40 ns |  38.5132 |     - |     - |  161280 B |
|         **ParseRawVarint32_CodedInputStream** |        **10080** |           **5** |  **19,614.0 ns** |   **278.86 ns** |   **260.84 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint32_ParseContext |        10080 |           5 |  19,419.7 ns |   368.14 ns |   752.01 ns |        - |     - |     - |         - |
|         ParseRawVarint64_CodedInputStream |        10080 |           5 |  22,013.9 ns |   224.74 ns |   210.22 ns |   0.0305 |     - |     - |     168 B |
|             ParseRawVarint64_ParseContext |        10080 |           5 |  20,962.6 ns |   277.36 ns |   259.44 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **6** |  **21,329.6 ns** |   **212.25 ns** |   **198.54 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           6 |  19,911.7 ns |   396.28 ns |   370.68 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **7** |  **20,025.3 ns** |   **291.28 ns** |   **272.46 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           7 |  19,608.6 ns |   256.76 ns |   214.41 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **8** |  **19,688.8 ns** |   **213.84 ns** |   **200.02 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           8 |  19,198.5 ns |   240.08 ns |   224.57 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |           **9** |  **19,380.4 ns** |   **263.97 ns** |   **246.92 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |           9 |  18,976.0 ns |   322.92 ns |   286.26 ns |        - |     - |     - |         - |
|         **ParseRawVarint64_CodedInputStream** |        **10080** |          **10** |  **19,063.2 ns** |   **170.36 ns** |   **151.02 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|             ParseRawVarint64_ParseContext |        10080 |          10 |  18,759.1 ns |   242.29 ns |   214.78 ns |        - |     - |     - |         - |
|              ParseString_CodedInputStream |        10080 |          10 |  35,486.4 ns |   686.67 ns |   868.41 ns |   9.6436 |     - |     - |   40488 B |
|                  ParseString_ParseContext |        10080 |          10 |  34,595.6 ns |   451.45 ns |   422.29 ns |   9.5825 |     - |     - |   40320 B |
|               ParseBytes_CodedInputStream |        10080 |          10 |  19,705.0 ns |   260.70 ns |   231.11 ns |  17.3645 |     - |     - |   72744 B |
|                   ParseBytes_ParseContext |        10080 |          10 |  20,396.9 ns |   403.23 ns |   673.71 ns |  17.3340 |     - |     - |   72576 B |
|              **ParseString_CodedInputStream** |        **10080** |         **105** |   **5,410.8 ns** |   **103.99 ns** |    **97.27 ns** |   **5.3635** |     **-** |     **-** |   **22440 B** |
|                  ParseString_ParseContext |        10080 |         105 |   5,262.6 ns |    88.87 ns |    78.78 ns |   5.3253 |     - |     - |   22272 B |
| ParseString_ParseContext_MultipleSegments |        10080 |         105 |   9,747.3 ns |   193.59 ns |   181.08 ns |   5.3253 |     - |     - |   22272 B |
|               ParseBytes_CodedInputStream |        10080 |         105 |   2,544.4 ns |    49.12 ns |    48.25 ns |   3.7117 |     - |     - |   15528 B |
|                   ParseBytes_ParseContext |        10080 |         105 |   2,501.4 ns |    45.43 ns |    42.49 ns |   3.6697 |     - |     - |   15360 B |
|  ParseBytes_ParseContext_MultipleSegments |        10080 |         105 |   5,711.1 ns |    84.68 ns |    79.21 ns |   3.6697 |     - |     - |   15360 B |
|              **ParseString_CodedInputStream** |        **10080** |       **10080** |   **1,870.4 ns** |    **19.96 ns** |    **18.67 ns** |   **4.8542** |     **-** |     **-** |   **20352 B** |
|                  ParseString_ParseContext |        10080 |       10080 |   1,786.8 ns |    30.80 ns |    28.81 ns |   4.8065 |     - |     - |   20184 B |
| ParseString_ParseContext_MultipleSegments |        10080 |       10080 |   3,811.4 ns |    37.70 ns |    33.42 ns |   4.8065 |     - |     - |   20184 B |
|               ParseBytes_CodedInputStream |        10080 |       10080 |     701.6 ns |    10.84 ns |    10.14 ns |   2.4567 |     - |     - |   10304 B |
|                   ParseBytes_ParseContext |        10080 |       10080 |     666.9 ns |    12.48 ns |    12.82 ns |   2.4204 |     - |     - |   10136 B |
|  ParseBytes_ParseContext_MultipleSegments |        10080 |       10080 |   2,433.3 ns |    48.59 ns |    59.67 ns |   2.4185 |     - |     - |   10136 B |
|             **ParseFixed32_CodedInputStream** |        **10080** |           **?** |  **29,762.4 ns** |   **157.58 ns** |   **147.41 ns** |   **0.0305** |     **-** |     **-** |     **168 B** |
|                 ParseFixed32_ParseContext |        10080 |           ? |  28,305.9 ns |   226.15 ns |   200.48 ns |        - |     - |     - |         - |
|             ParseFixed64_CodedInputStream |        10080 |           ? |  26,965.9 ns |   347.68 ns |   308.21 ns |   0.0305 |     - |     - |     168 B |
|                 ParseFixed64_ParseContext |        10080 |           ? |  26,059.3 ns |   167.06 ns |   156.27 ns |        - |     - |     - |         - |
|            ParseRawFloat_CodedInputStream |        10080 |           ? |  44,477.1 ns |   394.67 ns |   369.17 ns |        - |     - |     - |     168 B |
|                ParseRawFloat_ParseContext |        10080 |           ? |  43,062.7 ns |   584.58 ns |   518.21 ns |        - |     - |     - |         - |
|           ParseRawDouble_CodedInputStream |        10080 |           ? |  29,255.0 ns |   528.30 ns |   668.13 ns |        - |     - |     - |     168 B |
|               ParseRawDouble_ParseContext |        10080 |           ? |  27,629.3 ns |   197.82 ns |   175.36 ns |        - |     - |     - |         - |