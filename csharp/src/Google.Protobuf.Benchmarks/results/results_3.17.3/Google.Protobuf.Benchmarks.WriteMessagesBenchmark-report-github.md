``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|                                                               Method | messageCount |         Mean |      Error |     StdDev |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|--------------------------------------------------------------------- |------------- |-------------:|-----------:|-----------:|-------:|------:|------:|----------:|
|                                 **ManyWrapperFieldsMessage_ToByteArray** |            **?** |    **807.67 ns** |  **10.829 ns** |  **10.129 ns** | **0.0429** |     **-** |     **-** |     **184 B** |
|                    ManyWrapperFieldsMessage_WriteToCodedOutputStream |            ? |    517.48 ns |   7.457 ns |   6.611 ns | 0.0153 |     - |     - |      64 B |
|                                 ManyWrapperFieldsMessage_WriteToSpan |            ? |    502.40 ns |   7.506 ns |   7.021 ns |      - |     - |     - |         - |
|                               ManyPrimitiveFieldsMessage_ToByteArray |            ? |    395.53 ns |   5.978 ns |   5.300 ns | 0.0401 |     - |     - |     168 B |
|                  ManyPrimitiveFieldsMessage_WriteToCodedOutputStream |            ? |    294.19 ns |   4.604 ns |   4.307 ns | 0.0153 |     - |     - |      64 B |
|                               ManyPrimitiveFieldsMessage_WriteToSpan |            ? |    277.86 ns |   4.161 ns |   3.892 ns |      - |     - |     - |         - |
|                                             EmptyMessage_ToByteArray |            ? |     34.19 ns |   0.464 ns |   0.388 ns | 0.0210 |     - |     - |      88 B |
|                                EmptyMessage_WriteToCodedOutputStream |            ? |     27.50 ns |   0.562 ns |   0.526 ns | 0.0153 |     - |     - |      64 B |
|                                             EmptyMessage_WriteToSpan |            ? |     12.26 ns |   0.263 ns |   0.233 ns |      - |     - |     - |         - |
|   **ManyWrapperFieldsMessage_WriteDelimitedMessagesToCodedOutputStream** |           **10** |  **7,596.10 ns** | **137.738 ns** | **122.101 ns** | **0.0153** |     **-** |     **-** |      **64 B** |
|                ManyWrapperFieldsMessage_WriteDelimitedMessagesToSpan |           10 |  7,400.37 ns |  54.982 ns |  51.430 ns |      - |     - |     - |         - |
| ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToCodedOutputStream |           10 |  3,749.14 ns |  21.743 ns |  19.274 ns | 0.0153 |     - |     - |      64 B |
|              ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToSpan |           10 |  3,618.80 ns |  34.330 ns |  32.112 ns |      - |     - |     - |         - |
|   **ManyWrapperFieldsMessage_WriteDelimitedMessagesToCodedOutputStream** |          **100** | **75,962.50 ns** | **770.504 ns** | **683.032 ns** |      **-** |     **-** |     **-** |      **64 B** |
|                ManyWrapperFieldsMessage_WriteDelimitedMessagesToSpan |          100 | 74,091.77 ns | 966.210 ns | 806.829 ns |      - |     - |     - |         - |
| ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToCodedOutputStream |          100 | 36,914.20 ns | 505.599 ns | 472.938 ns |      - |     - |     - |      64 B |
|              ManyPrimitiveFieldsMessage_WriteDelimitedMessagesToSpan |          100 | 36,021.93 ns | 450.587 ns | 399.433 ns |      - |     - |     - |         - |
