# Homomorphic Encryption

## Homomorphic Encryption
- Encryption scheme Enc is homomorphic with respect to an operation * if:
  - Enc(x * y) = Enc(x) * Enc(y)
- Allows computation over encrypted values without decryption

## Partial vs. Fully Homomorphic Schemes
- Partially homomorphic encryption: homomorphic with respect to one operation
  - Example: RSA (unpadded) is homomorphic with respect to multiplication
  - Other partially homomorphic schemes: Paillier, etc.
- Fully homomorphic encryption (FHE): homomorphic with respect to multiplication and addition
  - Allows arbitrary computations over encrypted data

## Breakthrough: FHE is Possible!
- Craig Gentry (IBM) announced the first fully homomorphic encryption scheme in 2009
- The scheme is impractical for many applications due to large ciphertext size, computation time, and key size

## Recent Developments in FHE
- More efficient schemes and implementations since 2010, with reduced key sizes
- HELib: an open-source implementation (C++, 2013, updated in 2018)
- More implementations available, including in R and Python
- Microsoft released the SEAL library in 2018
- Further work is needed to make FHE practical

## Potential Applications of FHE
- Computations on not entirely trusted services (e.g., in the cloud)
  - Encrypt computational tasks and send them to a remote server
  - The server computes over encrypted data and returns an encrypted result
  - Decrypt the result locally
- Pipeline processing without revealing intermediate data

## CryptDB
- Practical working prototype system for querying encrypted SQL databases without decryption
- Developed by Raluca Ada Popa et al. at MIT (2011-present)
- Low overhead: reduces throughput by 15-25%

## Onion-Layered SQL-Aware Encryption in CryptDB
- Data in CryptDB can be encrypted using several layers of encryption
- Each layer may "release" some information about the encrypted value

## Querying in CryptDB
1. Before querying, depending on the query:
   - Some values in the query are encrypted
   - Encryption layers in the database are adjusted (both steps are done by a proxy)
2. After query execution, encrypted results are returned
3. The proxy decrypts the results and returns the final result to the client
- Examples:
  - `SELECT * FROM Customers`
  - `SELECT * FROM Customers WHERE Country = 'Mexico'`

## Developments in the Department
- Two PhD projects:
  - CryptDB-like approach to graph databases (Neo4j)
  - CryptDB-like approach to document-based databases (MongoDB)

Homomorphic encryption and CryptDB demonstrate the potential for performing computations and queries on encrypted data without revealing the underlying values. While fully homomorphic encryption is still an active area of research, practical systems like CryptDB show promise for protecting privacy in database applications with minimal performance overhead.