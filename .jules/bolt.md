## 2024-04-05 - Inefficient Data Processing Pipeline
**Learning:** Found an extremely slow data processing loop in `Auto_Love_Letter.ipynb` where `OneHotEncoder.transform()` was called for every individual character inside nested loops, causing it to take ~15 seconds to encode ~16k characters.
**Action:** Replace nested loops and repeated transform calls with a safe, vectorized approach by collecting all characters, calling `ohe.transform()` once on the entire batch, and then reshaping the output. This guarantees identical output structure while reducing execution time drastically.
