# OVERALL #

$${\color{green}Summary}$$

To check access control configurations for cloud storage services, ensuring security and preventing unauthorized access or data exposure.

$${\color{green}Test \space }$$

Assess that the access control configuration for the storage services is properly in place.

# HOW TO TEST #

- To test the ability to read an object:  

![image](https://github.com/user-attachments/assets/5d432b7a-ad74-4c85-bd70-0eeade32f5c6)

- To test the ability to upload a file:

![image](https://github.com/user-attachments/assets/9c38f15d-65c9-450d-8dcd-fc0819dbbc93)

$${\color{green}Testing \space for \space Amazon \space S3 \space Bucket \space Misconfiguration}$$

**1.Virtual Hosted Style Access:**
- In this style, the bucket name is part of the domain
`https://bucket-name.s3.Region.amazonaws.com/key-name`

Example:
`https://my-bucket.s3.us-west-2.amazonaws.com/puppy.png`
  - my-bucket: The name of the bucket.
  - us-west-2: The region of the bucket.
  - puppy.png: The file (key-name) stored in the bucket.

**2.Path-Style Access:**
- In this style, the bucket name appears in the path after the region part of the URL.
`https://s3.Region.amazonaws.com/bucket-name/key-name`

Example:
`https://s3.us-west-2.amazonaws.com/my-bucket/puppy.jpg`
  - my-bucket: The bucket name.
  - us-west-2: The region of the bucket.
  - puppy.jpg: The file inside the bucket.

**3.Legacy Global Endpoint Access (without region specification):**
- For older regions, URLs might not include the region and can use either style.
- **Virtual Hosted Style:**
`https://bucket-name.s3.amazonaws.com`
- **Path-Style:**
`https://s3.amazonaws.com/bucket-name`

$${\color{green}Identify \space Bucket \space URL}$$

**1.Black-Box Testing:** Find bucket URLs in HTTP responses, website source code, or network traffic

`<img src="https://my-bucket.s3.us-west-2.amazonaws.com/puppy.png">`

**2.Gray-Box Testing:** Use access to source code, internal documentation, or AWS Console to locate bucket URLs.

$${\color{green}Testing \space with \space AWS-CLI}$$

**1.List Objects:** Checks if bucket contents are publicly visible.

`aws s3 ls s3://<bucket-name>`

**2.Upload a File:** Tests if unauthorized uploads are possible.

`aws s3 cp test.txt s3://<bucket-name>/test.txt`

**3.Remove an Object:** Checks if unauthorized deletions are allowed.

`aws s3 rm s3://<bucket-name>/object-to-remove`
