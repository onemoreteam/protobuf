``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|             Method |          Dataset |     Mean |    Error |   StdDev |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------- |----------------- |---------:|---------:|---------:|-------:|------:|------:|----------:|
|      WriteToStream | goog_msg1_proto3 | 574.9 ns | 11.21 ns | 11.51 ns | 0.9995 |     - |     - |    4184 B |
|        ToByteArray | goog_msg1_proto3 | 471.9 ns |  9.20 ns |  8.60 ns | 0.0744 |     - |     - |     312 B |
| ParseFromByteArray | goog_msg1_proto3 | 564.7 ns | 10.83 ns | 11.59 ns | 0.2480 |     - |     - |    1040 B |
|    ParseFromStream | goog_msg1_proto3 | 818.7 ns | 16.12 ns | 23.62 ns | 1.2321 |     - |     - |    5160 B |
