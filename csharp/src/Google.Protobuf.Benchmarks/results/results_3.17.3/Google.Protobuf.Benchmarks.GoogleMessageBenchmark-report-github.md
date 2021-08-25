``` ini

BenchmarkDotNet=v0.12.1, OS=Windows 10.0.19043
Intel Core i7-6700 CPU 3.40GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=5.0.302
  [Host]     : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT
  DefaultJob : .NET Core 5.0.8 (CoreCLR 5.0.821.31504, CoreFX 5.0.821.31504), X64 RyuJIT


```
|             Method |          Dataset |     Mean |    Error |   StdDev |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------------- |----------------- |---------:|---------:|---------:|-------:|------:|------:|----------:|
|      WriteToStream | goog_msg1_proto3 | 607.0 ns | 11.73 ns | 12.05 ns | 0.9995 |     - |     - |    4184 B |
|        ToByteArray | goog_msg1_proto3 | 491.7 ns |  7.64 ns |  6.77 ns | 0.0744 |     - |     - |     312 B |
| ParseFromByteArray | goog_msg1_proto3 | 613.4 ns |  9.73 ns |  8.62 ns | 0.2480 |     - |     - |    1040 B |
|    ParseFromStream | goog_msg1_proto3 | 865.3 ns | 14.01 ns | 13.10 ns | 1.2321 |     - |     - |    5160 B |
