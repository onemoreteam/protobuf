``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                                                Method | messageCount |          Mean |        Error |       StdDev |    Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------------------------------------------------------------------- |------------- |--------------:|-------------:|-------------:|---------:|------:|------:|----------:|
|                           **ManyWrapperFieldsMessage_ParseFromByteArray** |            **?** |     **390.63 ns** |     **7.771 ns** |     **7.632 ns** |   **0.4644** |     **-** |     **-** |    **1944 B** |
|                    ManyWrapperFieldsMessage_ParseFromReadOnlySequence |            ? |     351.07 ns |     6.822 ns |     7.300 ns |   0.4244 |     - |     - |    1776 B |
|                         ManyPrimitiveFieldsMessage_ParseFromByteArray |            ? |     236.12 ns |     4.213 ns |     3.941 ns |   0.2637 |     - |     - |    1104 B |
|                  ManyPrimitiveFieldsMessage_ParseFromReadOnlySequence |            ? |     185.98 ns |     3.229 ns |     3.020 ns |   0.2236 |     - |     - |     936 B |
|                               RepeatedFieldMessage_ParseFromByteArray |            ? |   4,522.49 ns |    78.071 ns |    76.676 ns |   2.0142 |     - |     - |    8432 B |
|                        RepeatedFieldMessage_ParseFromReadOnlySequence |            ? |   4,566.46 ns |    65.607 ns |    61.369 ns |   1.9684 |     - |     - |    8264 B |
|                                       EmptyMessage_ParseFromByteArray |            ? |      91.77 ns |     1.497 ns |     1.400 ns |   0.0459 |     - |     - |     192 B |
|                                EmptyMessage_ParseFromReadOnlySequence |            ? |      42.08 ns |     0.622 ns |     0.582 ns |   0.0057 |     - |     - |      24 B |
|          **ManyWrapperFieldsMessage_ParseDelimitedMessagesFromByteArray** |           **10** |   **3,685.62 ns** |    **72.426 ns** |    **74.376 ns** |   **4.2801** |     **-** |     **-** |   **17928 B** |
|   ManyWrapperFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |           10 |   3,208.85 ns |    59.294 ns |    55.464 ns |   4.2458 |     - |     - |   17760 B |
|        ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromByteArray |           10 |   2,145.16 ns |    41.748 ns |    42.872 ns |   2.2774 |     - |     - |    9528 B |
| ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |           10 |   1,724.92 ns |    26.166 ns |    23.196 ns |   2.2373 |     - |     - |    9360 B |
|              RepeatedFieldMessage_ParseDelimitedMessagesFromByteArray |           10 |  44,786.14 ns |   327.889 ns |   290.665 ns |  19.7144 |     - |     - |   82808 B |
|       RepeatedFieldMessage_ParseDelimitedMessagesFromReadOnlySequence |           10 |  44,484.20 ns |   842.876 ns |   788.427 ns |  19.7144 |     - |     - |   82640 B |
|          **ManyWrapperFieldsMessage_ParseDelimitedMessagesFromByteArray** |          **100** |  **36,284.13 ns** |   **644.330 ns** |   **571.182 ns** |  **42.4805** |     **-** |     **-** |  **177768 B** |
|   ManyWrapperFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |          100 |  32,291.12 ns |   621.518 ns |   665.017 ns |  42.4194 |     - |     - |  177600 B |
|        ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromByteArray |          100 |  21,113.51 ns |   412.443 ns |   405.074 ns |  22.3999 |     - |     - |   93768 B |
| ManyPrimitiveFieldsMessage_ParseDelimitedMessagesFromReadOnlySequence |          100 |  16,455.02 ns |   232.654 ns |   194.277 ns |  22.3694 |     - |     - |   93600 B |
|              RepeatedFieldMessage_ParseDelimitedMessagesFromByteArray |          100 | 455,820.63 ns | 3,505.677 ns | 3,107.692 ns | 197.2656 |     - |     - |  826568 B |
|       RepeatedFieldMessage_ParseDelimitedMessagesFromReadOnlySequence |          100 | 450,935.94 ns | 6,868.618 ns | 6,424.910 ns | 196.7773 |     - |     - |  826400 B |
