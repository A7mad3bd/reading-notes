# Read 37

# What is Amazon S3?

- Amazon Simple Storage Service (Amazon S3) is an object storage service that offers scalability, data availability, security and performance.
- Users can store and protect any amount of data for a range of use cases (data lakes, websites, mobile apps, backup and restore, archive, enterprise apps, IoT devices and big data analytics)
- Provides management features to help organize, optimize and configure access to your data.

- Overall, a way to save costs on storage costs.
- S3 inteeligent tieering will optimize your storage for lower costs
- S3 Lifecycle A place to store your object for their life cycle
- S3 Object Lock are objkects that can't be updated or deleted
- S# Replication replicate your objects in destination buckets or AWS region
- S3 Batch Operations  for large scaled operations
- Amazon S3 provides access management services
- Data processing services

### Parts of S3

- Buckets : A bucket is a container for objects stored in S3.
- Objects : fundamental entities stored in S3.- Version ID : object is uniquely identified within a bucket by a key(name) and a version ID
- Bucket Policy : 
- S3 Access Points : are named network endpoints with dedicated access policies that describe how data can be access using that endpoint.
- Access control lists : use ACLs to grant read and write permissions to authorized users for individual buckets and objects (predates AIM).
- Regions : choose region where you want S3 to store the buckets you create.
- Keys
- S3 Versioning

#### Overview of S3 parts

- Buckets are containers for objects. You can store as many objects as needed with 100 buckets per account
    - You can request an increase of buckets if needed
- Objects are entities stored in S3. Stored in bucket by Key  and verion ID
- Keys are unique identifiers for objects in buckets
- S3 versioning allows you to keep several versions of the same object in a bucket
- Version ID are unique to version of the object
- AWS IAM policy that grants access and permission to buckets and the bucket owner can set the policy
- S3 Access Points are like object operations doing GetObject or PutObjects

#### Pricing

- AWS S3 only charges you for what you use pay as you go model.


## Storage - Getting started

````
amplify add storage

````

- Choose Defaults
````

        amplify push
````

- Dependencies
````

        dependencies {
        implementation 'com.amplifyframework:aws-storage-s3:1.34.0'
        implementation 'com.amplifyframework:aws-auth-cognito:1.34.0'
        }
````

//Initialize
//PlugIns
````

        Amplify.addPlugin(new AWSCognitoAuthPlugin());
        Amplify.addPlugin(new AWSS3StoragePlugin());
        ````

- Whole  class

public class MyAmplifyApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            // Add these lines to add the AWSCognitoAuthPlugin and AWSS3StoragePlugin plugins
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSS3StoragePlugin());
            Amplify.configure(getApplicationContext());

            Log.i("MyAmplifyApp", "Initialized Amplify");
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
}
````

// Uploading Data Bucket

````
private void uploadFile() {
        File exampleFile = new File(getApplicationContext().getFilesDir(), "ExampleKey");

        try {
        BufferedWriter writer = new BufferedWriter(new FileWriter(exampleFile));
        writer.append("Example file contents");
        writer.close();
        } catch (Exception exception) {
        Log.e("MyAmplifyApp", "Upload failed", exception);
        }

        Amplify.Storage.uploadFile(
        "ExampleKey",
        exampleFile,
        result -> Log.i("MyAmplifyApp", "Successfully uploaded: " + result.getKey()),
        storageFailure -> Log.e("MyAmplifyApp", "Upload failed", storageFailure)
        );
        }


````

 Resorces
- [What is Amazon S3?](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html#S3Features)
- [Storage](https://docs.amplify.aws/lib/storage/getting-started/q/platform/android/#provision-backend-storage)


