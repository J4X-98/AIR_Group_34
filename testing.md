**Specs**
* 100 < Price 500.000
* loss='mean_absolute_percentage_error', optimizer'adam', activation='relu'/'linear', batch_size = 64

384->352->448->160->160->32->1-->[{ END 25 rounds mae = 1737, 30%}] <br />
256(0.05)-->128(0.01)-->64(0.005)-->32(0.001)[{30 rounds mae = 1760, 30%} {END 39 rounds mae = 1702, 29.5%}] <br />
256-->128-->64[{END 26 rounds mae = 1778, 30%}] <br />
256-->128-->[{30 rounds mae = 1828, 31.5%}, {END 33 rounds mae = 1809, 30%}] <br />
256-->[{30 rounds mae = 1887, 31%}, {END 38 rounds mae = 1868, 31%}] <br />
64-->8[{30 rounds mae = 1872, 32%}] <br />
no hidden layer -> [{30 rounds mae = 2441, 35%}] <br />

**Specs**
* 100 < Price 500.000
* loss='mean_absolute_percentage_error', optimizer'adam', activation='relu'/'linear', batch_size = 64
* No early stop
256(0.05)-->128(0.01)-->64(0.005)-->32(0.001)[{67 rounds mae = 1686, 29%}] <br />

**SPECS**
* 100 < Price 500.000
* numerical values not normalized
* loss='mean_absolute_percentage_error', optimizer'adam', activation='relu'/'linear', batch_size = 64
* No early stop
256(0.05)-->128(0.01)-->64(0.005)-->32(0.001)[{70 rounds mae = 2589, 40%}] <br />

**SPECS**
* 100 < Price 500.000
* dropped 'fuelType', 'brand', 'gearbox'
* loss='mean_absolute_percentage_error', optimizer'adam', activation='relu'/'linear', batch_size = 64
* No early stop
256(0.05)-->128(0.01)-->64(0.005)-->32(0.001)[{60 rounds mae = 1865, 31.5%}] <br />

**SPECS**
* 100 < Price 500.000
* loss='mean_absolute_percentage_error', optimizer'adam', activation='relu'/'linear', batch_size = 64
* No early stop
256(0.05)-->128(0.01)-->64(0.005)-->32(0.001)[{100 rounds mae = 1639, 28%} HOWEVER TESTDATA STILL mae = 1780 33%] <br />

**Specs:**
- 100 < Price < 500.000
- loss='mean_absolute_error', optimizer='adam', activation='relu'/'linear', batch_size=256

256 -> 128 -> 64 -> 32 ->16 -> 8 -> 4 -> 2  --> [{30 rounds mae = 1484, 36%}, {END 45 rounds mae = 1430, 34.75%}] <br />
**BEST!!!**  128 -> 64 -> 32 ->16 -> 8 -> 4 -> 2         --> [{30 rounds mae = 1502, 36.2%}, {END 54 rounds mae = 1428, 34.97%}] <br />
155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2       --> [{30 rounds mae = 1478, 36%}, {END 34 rounds mae = 1484, 36%}] <br />
155 -> 64 -> 39 -> 20 -> 10 -> 5            --> [mae = 1478 (30 rounds)] <br />
155 -> 64 -> 39 -> 20 -> 10                 --> [mae = 1483 (30 rounds)] <br />
155 -> 64 -> 39 -> 20                       --> [mae = 1489 (30 rounds)] <br />
155 -> 64 -> 39                             --> [mae = 1499 (30 rounds)] <br />
155 -> 64                                   --> [mae = 1525 (30 rounds)] <br />
155(DO) -> 64(DO)                           --> [mae = 1641 (30 rounds)] <br />

**Specs:**
- 100 < Price < 500.000
- loss='huber_loss', optimizer='adam', activation='relu'/'linear', batch_size=256

155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2  --> [mae = 1500 (30 rounds)] <br />

**Specs:**
- 100 < Price < 500.000
- loss='mean_squared_error', optimizer='adam', activation='relu'/'linear', batch_size=256

155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2  --> [mae = ~6900 (30 rounds)] <br />

**Specs:**
- 100 < Price < 100.000
- loss='mean_absolute_error', optimizer='adam', activation='relu'/'linear', batch_size=256

155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2  --> [{30 rounds mae = ~1428, 36%}, {END 31 rounds mae = ~1425, 36%}] <br />

**Specs:**
- 100 < Price < 500.000
- loss='mean_absolute_error', optimizer='adam', activation='relu'/'linear', batch_size=128

155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2  --> [{30 rounds mae = 1475, 35%}, {END 42 rounds mae = 1443, 35%}] <br />

**Specs:**
- 100 < Price < 500.000
- loss='mean_absolute_error', optimizer='adam', activation='relu'/'linear', batch_size=64

155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2       --> [{30 rounds mae = 1470, 35.5%}, {END 49 rounds mae = 1452, 35.19%}] <br />
155 -> 64 -> 32 -> 16 -> 8 -> 4 -> 2        -->  [{END 2 rounds mae = 1498, 35%}] <br />
128 -> 64 -> 32 ->16 -> 8 -> 4 -> 2         --> [{END 25 rounds mae = 1489, 35.84%}] <br />

**Specs:**
- 100 < Price < 500.000
- loss='mean_absolute_error', optimizer='adam', activation='relu'/'linear', batch_size=32

155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2  --> [{END 28 rounds mae = 1472, 36%}] <br />

**Findings:**
- Cutting of over 100k instead of 500k changes the difference in euro by a bit but not the percent accuracy
- mean abolute error best loss
- 155 -> 64 -> 39 -> 20 -> 10 -> 5 -> 2 best layer structure
- relu/linear best activation
- adam best optimizer
- sometimes gets stuck at ~6900
