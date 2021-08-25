``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                Method | BytesToWrite | encodedSize |           Mean |         Error |        StdDev |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|-------------------------------------- |------------- |------------ |---------------:|--------------:|--------------:|-------:|------:|------:|----------:|
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **1** |  **33,546.996 ns** |   **306.8743 ns** |   **272.0361 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           1 |  26,831.657 ns |   291.3948 ns |   272.5709 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           1 |  34,080.617 ns |   464.0259 ns |   434.0501 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           1 |  26,848.553 ns |   352.2782 ns |   329.5213 ns |      - |     - |     - |         - |
|         WriteString_CodedOutputStream |        10080 |           1 | 190,917.235 ns | 1,062.6096 ns |   941.9757 ns |      - |     - |     - |      64 B |
|              WriteString_WriteContext |        10080 |           1 | 167,385.289 ns | 3,043.3281 ns | 2,697.8311 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |           1 | 116,011.048 ns |   961.9611 ns |   899.8190 ns |      - |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |           1 | 110,381.107 ns | 1,714.4988 ns | 1,431.6842 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **2** |  **27,058.622 ns** |   **357.5773 ns** |   **334.4780 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           2 |  25,928.318 ns |   248.6384 ns |   232.5765 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           2 |  26,174.560 ns |   214.5196 ns |   179.1336 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           2 |  26,274.646 ns |   343.0338 ns |   304.0905 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **3** |  **26,198.077 ns** |   **273.9515 ns** |   **228.7619 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           3 |  25,080.381 ns |   183.2058 ns |   171.3708 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           3 |  26,040.873 ns |   231.4728 ns |   216.5198 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           3 |  24,999.521 ns |   185.8175 ns |   145.0741 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **4** |  **25,329.038 ns** |   **171.7474 ns** |   **152.2496 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           4 |  24,458.275 ns |   258.2008 ns |   241.5212 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           4 |  25,420.286 ns |   346.3946 ns |   324.0178 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           4 |  24,311.689 ns |   208.6740 ns |   174.2522 ns |      - |     - |     - |         - |
|         WriteString_CodedOutputStream |        10080 |           4 |  48,762.710 ns |   504.7012 ns |   472.0978 ns |      - |     - |     - |      64 B |
|              WriteString_WriteContext |        10080 |           4 |  43,186.768 ns |   460.0201 ns |   430.3031 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |           4 |  58,977.662 ns |   403.7553 ns |   357.9186 ns |      - |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |           4 |  53,074.342 ns |   410.6645 ns |   384.1359 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |           4 |  29,805.698 ns |   350.2232 ns |   327.5990 ns |      - |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |           4 |  28,476.570 ns |   332.0743 ns |   310.6225 ns |      - |     - |     - |         - |
|    **WriteRawVarint32_CodedOutputStream** |        **10080** |           **5** |  **24,709.000 ns** |   **227.2553 ns** |   **212.5748 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint32_WriteContext |        10080 |           5 |  23,923.761 ns |   122.4067 ns |    95.5671 ns |      - |     - |     - |         - |
|    WriteRawVarint64_CodedOutputStream |        10080 |           5 |  24,742.600 ns |   318.2565 ns |   297.6973 ns |      - |     - |     - |      64 B |
|         WriteRawVarint64_WriteContext |        10080 |           5 |  24,186.975 ns |   251.8999 ns |   235.6274 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **6** |  **24,450.746 ns** |   **221.7731 ns** |   **196.5961 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           6 |  23,966.794 ns |   205.9952 ns |   192.6881 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **7** |  **24,259.697 ns** |   **190.2385 ns** |   **177.9492 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           7 |  24,148.027 ns |   441.0967 ns |   391.0207 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **8** |  **24,923.157 ns** |   **337.7555 ns** |   **315.9367 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           8 |  23,897.675 ns |   337.0477 ns |   298.7840 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |           **9** |  **24,371.997 ns** |   **147.2251 ns** |   **137.7144 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |           9 |  23,572.384 ns |   222.4761 ns |   208.1043 ns |      - |     - |     - |         - |
|    **WriteRawVarint64_CodedOutputStream** |        **10080** |          **10** |  **24,046.973 ns** |   **152.2813 ns** |   **127.1618 ns** |      **-** |     **-** |     **-** |      **64 B** |
|         WriteRawVarint64_WriteContext |        10080 |          10 |  23,604.864 ns |   309.5136 ns |   274.3757 ns |      - |     - |     - |         - |
|         WriteString_CodedOutputStream |        10080 |          10 |  20,713.519 ns |   408.7713 ns |   419.7781 ns |      - |     - |     - |      64 B |
|              WriteString_WriteContext |        10080 |          10 |  18,570.173 ns |   353.3070 ns |   406.8688 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |          10 |  25,015.120 ns |   276.8383 ns |   258.9547 ns |      - |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |          10 |  23,031.145 ns |   292.3483 ns |   273.4628 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |          10 |  11,428.878 ns |   143.3080 ns |   134.0504 ns | 0.0153 |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |          10 |  10,834.654 ns |   108.1722 ns |   101.1843 ns |      - |     - |     - |         - |
|         **WriteString_CodedOutputStream** |        **10080** |         **105** |   **4,492.207 ns** |    **81.2760 ns** |    **76.0257 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|              WriteString_WriteContext |        10080 |         105 |   4,377.620 ns |    54.9834 ns |    48.7414 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |         105 |   7,957.847 ns |    90.2907 ns |    84.4580 ns | 0.0153 |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |         105 |   7,871.282 ns |    92.9650 ns |    86.9595 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |         105 |   1,309.135 ns |    16.4966 ns |    14.6238 ns | 0.0153 |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |         105 |   1,217.929 ns |    23.3196 ns |    24.9517 ns |      - |     - |     - |         - |
|         **WriteString_CodedOutputStream** |        **10080** |       **10080** |   **2,919.839 ns** |    **43.9920 ns** |    **38.9978 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|              WriteString_WriteContext |        10080 |       10080 |   2,905.801 ns |    36.0071 ns |    33.6810 ns |      - |     - |     - |         - |
| WriteNonAsciiString_CodedOutputStream |        10080 |       10080 |   4,545.312 ns |    43.5249 ns |    40.7132 ns | 0.0153 |     - |     - |      64 B |
|      WriteNonAsciiString_WriteContext |        10080 |       10080 |   4,499.643 ns |    32.7095 ns |    27.3139 ns |      - |     - |     - |         - |
|          WriteBytes_CodedOutputStream |        10080 |       10080 |     204.024 ns |     2.1767 ns |     2.0360 ns | 0.0153 |     - |     - |      64 B |
|               WriteBytes_WriteContext |        10080 |       10080 |     190.790 ns |     1.5343 ns |     1.3601 ns |      - |     - |     - |         - |
|        **WriteFixed32_CodedOutputStream** |        **10080** |           **?** |  **31,139.305 ns** |   **443.1924 ns** |   **370.0857 ns** |      **-** |     **-** |     **-** |      **64 B** |
|             WriteFixed32_WriteContext |        10080 |           ? |  29,716.341 ns |   380.9786 ns |   356.3676 ns |      - |     - |     - |         - |
|        WriteFixed64_CodedOutputStream |        10080 |           ? |  28,802.569 ns |   313.9145 ns |   293.6358 ns |      - |     - |     - |      64 B |
|             WriteFixed64_WriteContext |        10080 |           ? |  28,456.529 ns |   293.1611 ns |   274.2231 ns |      - |     - |     - |         - |
|      WriteRawTag_OneByte_WriteContext |        10080 |           ? |  27,713.106 ns |   336.6327 ns |   314.8864 ns |      - |     - |     - |         - |
|     WriteRawTag_TwoBytes_WriteContext |        10080 |           ? |  18,840.867 ns |   268.8631 ns |   238.3401 ns |      - |     - |     - |         - |
|   WriteRawTag_ThreeBytes_WriteContext |        10080 |           ? |  17,739.879 ns |   233.3387 ns |   194.8484 ns |      - |     - |     - |         - |
|                 Baseline_WriteContext |        10080 |           ? |       3.611 ns |     0.0581 ns |     0.0543 ns |      - |     - |     - |         - |
|       WriteRawFloat_CodedOutputStream |        10080 |           ? |  32,247.814 ns |   452.8976 ns |   401.4820 ns |      - |     - |     - |      64 B |
|            WriteRawFloat_WriteContext |        10080 |           ? |  30,686.329 ns |   465.7982 ns |   435.7080 ns |      - |     - |     - |         - |
|      WriteRawDouble_CodedOutputStream |        10080 |           ? |  29,470.446 ns |   256.7986 ns |   227.6453 ns |      - |     - |     - |      64 B |
|           WriteRawDouble_WriteContext |        10080 |           ? |  26,476.769 ns |   237.0773 ns |   221.7623 ns |      - |     - |     - |         - |
