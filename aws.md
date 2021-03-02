# S3 - Simple Storage Service

+ S3 is Object-based storage for files (from 0 bytes to 5 TB)

+ Buckets (think folders) must have unique names because S3 is globally universal

+ Reads of new files are available immediately; reads of updates or deletes may take some time.

+ Guarantees 99.99999999999% durability for S3 information

+ Some features that S3 offers are: Tiered Storage, Lifecycle Management, Versioning, MFA Deletion, Bucket Policies and
  Access Control Lists to secure data.

+ S3 Standard features 99.99% availability, 99.99999999999% durability, is stored redundantly across multiple devices in
  multiple facilities, is designed to sustain the loss of 2 concurrent facilities.

+ S3 - IA is for data that is Infrequently Accessed, but needs quick retrieval when it is accessed. Cheaper than
  standard S3, but comes with a retrieval fee.

+ S3 One Zone IA is like IA but doesn't have multiple Availability Zone data resilience. (Previously known as RRS)

+ S3 Intelligent Tiering optimizes costs by moving data into the most cost-effective tier.

+ S3 Glacier is a secure, durable, and low-cost storage class for data archiving. You can reliably store any amount of data
  at costs that compete with or are lower than on-premise solutions. Retrieval times can be configured to range from minutes to hours.

+ S3 Glacier Deep Archive is the lowest cost storage class where a retrival time of 12 hours is acceptable.

+ Storage charges include storage, requests, storage mgmt pricing, data transfer pricing, transfer acceleration, and cross-region replication pricing.

+ Cross-Region Replication:
  1) Versioning must be enabled on both source and destination buckets.
  2) Regions must be unique.
  3) Files in an existing bucket are not replicated automatically.
  4) All subsequent updated files will be replicated automatically.
  5) Delete markers will not be replicated.
  6) Deleting individual versions or delete markers will not be replicated.

+ Transfer Acceleration:
  1) Uploads to an edge location instead of a specific bucket.

## Creating an S3 Bucket

1) Navigate to S3 in the AWS dashboard
2) Select "Create Bucket" in the "Buckets" page in the S3 dashboard
3) Select a unique name for the bucket
4) Adjust default privacy settings (if necessary)
5) Upload necessary files into bucket


# Cloudfront

+ Cloudfront is a CDN
+ An Edge Location is the location where content will be cached.
+ An Origin is the origin of files that the CDN will distribute, like an S3 Bucket, and EC2 instance, etc.
+ A Distribution is a name given to the CDN, which is a collection of Edge Locations.
+ A Web Distribution is used for websites.
+ An RTMP is used for media streaming.
+ Edge locations can be read and written to
+ Objects care cached for the life of the TTL (Time To Live).
+ You CAN invalidate cached objects, but a charge comes with this.

# Snowball

+ Snowball is a petabyte-scale data transport solution.



