``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                Method | BytesToWrite | encodedSize |           Mean |         Error |        StdDev |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|-------------------------------------- |------------- |------------ |---------------:|--------------:|--------------:|-------:|------:|------:|----------:|
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **1** |  **34,228.572 ns** |   **526.4204 ns** |   **466.6580 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           1 |  27,080.389 ns |   497.5955 ns |   415.5147 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           1 |  33,764.230 ns |   414.4758 ns |   346.1061 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           1 |  26,850.363 ns |   448.9802 ns |   419.9764 ns |      - |     - |     - |         - |
|         WriteString_CodedOutputStream |        10080 |           1 | 193,291.925 ns | 3,705.8453 ns | 3,805.6302 ns |      - |     - |     - |      64 B |
|              WriteString_WriteContext |        10080 |           1 | 170,497.032 ns | 2,967.6168 ns | 5,274.9359 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |           1 | 115,289.419 ns | 1,023.6148 ns |   957.4899 ns |      - |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |           1 | 110,028.996 ns |   894.1927 ns |   792.6786 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **2** |  **27,211.720 ns** |   **522.0519 ns** |   **488.3277 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           2 |  26,327.013 ns |   341.8782 ns |   319.7931 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           2 |  26,925.892 ns |   193.1760 ns |   171.2455 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           2 |  26,606.220 ns |   453.2024 ns |   423.9258 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **3** |  **26,169.337 ns** |   **489.7179 ns** |   **458.0824 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           3 |  24,966.562 ns |   252.8553 ns |   236.5210 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           3 |  25,098.752 ns |   236.9998 ns |   221.6897 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           3 |  25,473.983 ns |   371.8123 ns |   347.7935 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **4** |  **25,260.262 ns** |   **193.5415 ns** |   **171.5695 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           4 |  24,637.892 ns |   284.1718 ns |   265.8145 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           4 |  25,477.266 ns |   281.4506 ns |   249.4986 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           4 |  24,575.323 ns |   299.8796 ns |   280.5075 ns |      - |     - |     - |         - |
|         WriteString_CodedOutputStream |        10080 |           4 |  49,249.355 ns |   528.7555 ns |   494.5983 ns |      - |     - |     - |      64 B |
|              WriteString_WriteContext |        10080 |           4 |  43,633.199 ns |   833.7990 ns |   739.1411 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |           4 |  59,282.841 ns |   680.5052 ns |   636.5450 ns |      - |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |           4 |  53,159.519 ns |   523.2823 ns |   489.4786 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |           4 |  29,725.664 ns |   291.3999 ns |   272.5757 ns |      - |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |           4 |  28,324.045 ns |   276.5596 ns |   245.1629 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **5** |  **24,384.959 ns** |   **125.9149 ns** |   **117.7809 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           5 |  24,024.398 ns |   165.8141 ns |   155.1026 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           5 |  24,600.025 ns |   295.0284 ns |   275.9697 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           5 |  24,215.923 ns |   297.6609 ns |   263.8687 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **6** |  **24,340.686 ns** |   **224.4615 ns** |   **209.9614 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           6 |  23,900.871 ns |   240.1107 ns |   224.5997 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **7** |  **24,137.950 ns** |   **359.0968 ns** |   **318.3300 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           7 |  23,680.790 ns |   102.9584 ns |    91.2699 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **8** |  **24,001.745 ns** |   **306.4684 ns** |   **255.9150 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           8 |  23,532.358 ns |   151.7090 ns |   134.4861 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **9** |  **23,739.175 ns** |   **180.2501 ns** |   **168.6060 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           9 |  23,440.232 ns |   178.5713 ns |   158.2988 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |          **10** |  **23,904.668 ns** |   **195.9818 ns** |   **183.3215 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |          10 |  23,510.903 ns |   181.3014 ns |   160.7190 ns |      - |     - |     - |         - |
|         WriteString_CodedOutputStream |        10080 |          10 |  20,591.466 ns |   256.3564 ns |   227.2532 ns |      - |     - |     - |      64 B |
|              WriteString_WriteContext |        10080 |          10 |  18,270.243 ns |   205.1083 ns |   191.8585 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |          10 |  24,977.499 ns |   212.6099 ns |   188.4731 ns |      - |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |          10 |  22,993.592 ns |   254.5759 ns |   238.1305 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |          10 |  11,411.591 ns |   150.1692 ns |   140.4684 ns | 0.0153 |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |          10 |  10,751.064 ns |    80.8889 ns |    71.7059 ns |      - |     - |     - |         - |
|         **WriteString_CodedOutputStream** |        **10080** |         **105** |   **4,472.358 ns** |    **55.4035 ns** |    **51.8244 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|              WriteString_WriteContext |        10080 |         105 |   4,368.549 ns |    71.7475 ns |    67.1127 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |         105 |   8,030.260 ns |   114.8676 ns |   107.4472 ns | 0.0153 |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |         105 |   7,764.836 ns |   149.1927 ns |   171.8105 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |         105 |   1,315.149 ns |    17.2627 ns |    15.3029 ns | 0.0153 |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |         105 |   1,217.040 ns |    11.6448 ns |    10.8926 ns |      - |     - |     - |         - |
|         **WriteString_CodedOutputStream** |        **10080** |       **10080** |   **2,913.344 ns** |    **37.2691 ns** |    **34.8616 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|              WriteString_WriteContext |        10080 |       10080 |   2,902.439 ns |    30.3652 ns |    28.4037 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |       10080 |   4,394.379 ns |    64.9429 ns |    60.7476 ns | 0.0153 |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |       10080 |   4,531.486 ns |    52.7447 ns |    44.0442 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |       10080 |     207.383 ns |     2.2892 ns |     2.0293 ns | 0.0153 |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |       10080 |     196.231 ns |     2.3545 ns |     2.2024 ns |      - |     - |     - |         - |
|        **WriteFixed32_CodedOutputStream** |        **10080** |           **?** |   **6,441.074 ns** |    **93.7212 ns** |    **87.6669 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|             WriteFixed32_WriteContext |        10080 |           ? |   6,104.370 ns |    42.8586 ns |    35.7889 ns |      - |     - |     - |         - |
|        WriteFixed64_CodedOutputStream |        10080 |           ? |   3,216.868 ns |    44.4340 ns |    41.5636 ns | 0.0153 |     - |     - |      64 B |
|             WriteFixed64_WriteContext |        10080 |           ? |   3,011.949 ns |    25.5994 ns |    22.6932 ns |      - |     - |     - |         - |
|      WriteRawTag_OneByte_WriteContext |        10080 |           ? |  26,828.073 ns |   311.6010 ns |   291.4718 ns |      - |     - |     - |         - |
|     WriteRawTag_TwoBytes_WriteContext |        10080 |           ? |  19,107.055 ns |   149.5744 ns |   132.5938 ns |      - |     - |     - |         - |
|   WriteRawTag_ThreeBytes_WriteContext |        10080 |           ? |  18,152.196 ns |   320.1449 ns |   507.7837 ns |      - |     - |     - |         - |
|                 Baseline_WriteContext |        10080 |           ? |       3.466 ns |     0.0983 ns |     0.0871 ns |      - |     - |     - |         - |
|       WriteRawFloat_CodedOutputStream |        10080 |           ? |   8,425.842 ns |   159.6475 ns |   141.5234 ns | 0.0153 |     - |     - |      64 B |
|            WriteRawFloat_WriteContext |        10080 |           ? |   6,796.652 ns |    60.0564 ns |    56.1768 ns |      - |     - |     - |         - |
|      WriteRawDouble_CodedOutputStream |        10080 |           ? |   2,973.144 ns |    32.5651 ns |    30.4614 ns | 0.0153 |     - |     - |      64 B |
|           WriteRawDouble_WriteContext |        10080 |           ? |   3,938.757 ns |    47.9674 ns |    44.8687 ns |      - |     - |     - |         - |
