``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                                                Method | messageCount |            Mean |         Error |        StdDev |    Gen 0 |  Gen 1 | Gen 2 | Allocated |
|---------------------------------------------------------------------- |------------- |----------------:|--------------:|--------------:|---------:|-------:|------:|----------:|
|                           **ManyWrapperFieldsMessage_ParseFromByteArray** |            **?** |       **502.57 ns** |      **8.289 ns** |      **7.754 ns** |   **0.4644** |      **-** |     **-** |    **1944 B** |
|                    ManyWrapperFieldsMessage_ParseFromReadOnlySequence |            ? |       465.91 ns |      6.240 ns |      5.836 ns |   0.4244 |      - |     - |    1776 B |
|                         ManyPrimitiveFieldsMessage_ParseFromByteArray |            ? |       361.73 ns |      5.299 ns |      4.957 ns |   0.2637 |      - |     - |    1104 B |
|                  ManyPrimitiveFieldsMessage_ParseFromReadOnlySequence |            ? |       296.73 ns |      5.924 ns |      5.542 ns |   0.2236 |      - |     - |     936 B |
|                               RepeatedFieldMessage_ParseFromByteArray |            ? |    22,816.80 ns |    259.420 ns |    229.969 ns |   2.0142 |      - |     - |    8432 B |
|                        RepeatedFieldMessage_ParseFromReadOnlySequence |            ? |    23,301.61 ns |    248.751 ns |    232.682 ns |   1.9531 | 0.0305 |     - |    8264 B |
|                                       EmptyMessage_ParseFromByteArray |            ? |        90.81 ns |      1.478 ns |      1.383 ns |   0.0459 |      - |     - |     192 B |
|                                EmptyMessage_ParseFromReadOnlySequence |            ? |        42.44 ns |      0.639 ns |      0.567 ns |   0.0057 |      - |     - |      24 B |
|          **ManyWrapperFieldsMessage_ParseDelimitedMessagesFromByteArray** |           **10** |     **4,918.26 ns** |     **95.898 ns** |    **121.280 ns** |   **4.2801** |      **-** |     **-** |   **17928 B** |
|   ManyWrapperFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |           10 |     4,594.24 ns |     86.166 ns |     92.196 ns |   4.2419 |      - |     - |   17760 B |
|        ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromByteArray |           10 |     3,212.55 ns |     52.493 ns |     49.102 ns |   2.2774 |      - |     - |    9528 B |
| ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |           10 |     2,862.65 ns |     48.551 ns |     45.415 ns |   2.2354 |      - |     - |    9360 B |
|              RepeatedFieldMessage_ParseDelimitedMessagesFromByteArray |           10 |   227,533.93 ns |  1,110.191 ns |    927.060 ns |  19.5313 |      - |     - |   82808 B |
|       RepeatedFieldMessage_ParseDelimitedMessagesFromReadOnlySequence |           10 |   251,709.85 ns |  3,024.495 ns |  2,829.114 ns |  19.5313 |      - |     - |   82640 B |
|          **ManyWrapperFieldsMessage_ParseDelimitedMessagesFromByteArray** |          **100** |    **48,959.12 ns** |    **952.199 ns** |    **977.838 ns** |  **42.4805** |      **-** |     **-** |  **177768 B** |
|   ManyWrapperFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |          100 |    44,630.36 ns |    881.469 ns |    865.721 ns |  42.4194 |      - |     - |  177600 B |
|        ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromByteArray |          100 |    31,988.61 ns |    521.557 ns |    487.865 ns |  22.3999 |      - |     - |   93768 B |
| ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |          100 |    28,401.73 ns |    412.714 ns |    386.053 ns |  22.3694 |      - |     - |   93600 B |
|              RepeatedFieldMessage_ParseDelimitedMessagesFromByteArray |          100 | 2,295,917.68 ns | 33,185.432 ns | 31,041.674 ns | 195.3125 |      - |     - |  826568 B |
|       RepeatedFieldMessage_ParseDelimitedMessagesFromReadOnlySequence |          100 | 2,520,903.75 ns | 23,468.473 ns | 21,952.424 ns | 195.3125 |      - |     - |  826400 B |
