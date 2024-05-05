Create a flexible file storage solution using an object store interface that supports operations for storing, retrieving, removing, and listing files. The solution should support multiple object store backends (e.g., S3, MinIO, Ceph) which can be swapped at runtime. This should be implemented using Java 1.8 and Spring Boot 2.5.15. The interface should provide the following operations:

1. **Store File**:
   * Accept a file and metadata, store it in the object store, and return the path or URL where the file is stored.

2. **Retrieve File**:
   * Retrieve a file by its unique identifier (e.g., file name, ID, or custom metadata).

3. **Remove File**:
   * Remove a file from the object store using its unique identifier.

4. **List Files**:
   * List files based on metadata filters like date range, file name, or ID. The listing operation should support filters such as:

     * **Date Range**: List files created or modified within a specific date range.
     * **File Name/ID**: List files matching a specific name or ID.

5. **Runtime Swapping of Implementations**:
   * The object store backend (e.g., S3, MinIO, Ceph) should be configurable and able to be switched at runtime without modifying the application's code. Use a configuration mechanism (e.g., Spring Profiles, dependency injection) to select the appropriate implementation.

6. **Flexibility in Storage Backend**:
   * The object store interface should be generic enough to allow for easy addition of new storage providers. The implementation should allow for runtime configuration of the backend (S3, MinIO, Ceph, etc.).