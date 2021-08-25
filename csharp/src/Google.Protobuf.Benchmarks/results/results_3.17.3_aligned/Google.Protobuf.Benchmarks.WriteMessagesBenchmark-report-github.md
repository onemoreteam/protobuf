``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                                               Method | messageCount |         Mean |      Error |     StdDev |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|--------------------------------------------------------------------- |------------- |-------------:|-----------:|-----------:|-------:|------:|------:|----------:|
|                                 **ManyWrapperFieldsMessage_ToByteArray** |            **?** |    **663.16 ns** |  **11.978 ns** |  **10.618 ns** | **0.0439** |     **-** |     **-** |     **184 B** |
|                    ManyWrapperFieldsMessage_WriteToCodedOutputStream |            ? |    402.87 ns |   6.383 ns |   5.659 ns | 0.0153 |     - |     - |      64 B |
|                                 ManyWrapperFieldsMessage_WriteToSpan |            ? |    373.63 ns |   5.748 ns |   4.800 ns |      - |     - |     - |         - |
|                               ManyPrimitiveFieldsMessage_ToByteArray |            ? |    274.33 ns |   5.347 ns |   4.465 ns | 0.0396 |     - |     - |     168 B |
|                  ManyPrimitiveFieldsMessage_WriteToCodedOutputStream |            ? |    179.12 ns |   2.484 ns |   2.324 ns | 0.0153 |     - |     - |      64 B |
|                               ManyPrimitiveFieldsMessage_WriteToSpan |            ? |    159.48 ns |   2.659 ns |   2.357 ns |      - |     - |     - |         - |
|                                             EmptyMessage_ToByteArray |            ? |     35.98 ns |   0.752 ns |   1.585 ns | 0.0210 |     - |     - |      88 B |
|                                EmptyMessage_WriteToCodedOutputStream |            ? |     27.06 ns |   0.561 ns |   0.525 ns | 0.0153 |     - |     - |      64 B |
|                                             EmptyMessage_WriteToSpan |            ? |     12.47 ns |   0.167 ns |   0.148 ns |      - |     - |     - |         - |
|   **ManyWrapperFieldsMessage_WriteDelimitedMessagesToCodedOutputStream** |           **10** |  **6,332.75 ns** | **121.099 ns** | **148.720 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|                ManyWrapperFieldsMessage_WriteDelimitedMessagesToSpan |           10 |  6,101.79 ns |  49.927 ns |  44.259 ns |      - |     - |     - |         - |
| ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToCodedOutputStream |           10 |  2,452.59 ns |  29.319 ns |  27.425 ns | 0.0153 |     - |     - |      64 B |
|              ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToSpan |           10 |  2,349.85 ns |  24.569 ns |  19.182 ns |      - |     - |     - |         - |
|   **ManyWrapperFieldsMessage_WriteDelimitedMessagesToCodedOutputStream** |          **100** | **63,836.02 ns** | **990.242 ns** | **926.273 ns** |      **-** |     **-** |     **-** |      **64 B** |
|                ManyWrapperFieldsMessage_WriteDelimitedMessagesToSpan |          100 | 60,443.38 ns | 524.220 ns | 490.356 ns |      - |     - |     - |         - |
| ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToCodedOutputStream |          100 | 24,429.44 ns | 213.331 ns | 189.112 ns |      - |     - |     - |      64 B |
|              ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToSpan |          100 | 23,727.34 ns | 370.875 ns | 328.771 ns |      - |     - |     - |         - |
