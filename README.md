This is the _unofficial_ MinIO Dart Client SDK that provides simple APIs to access any Amazon S3 compatible object storage server.

![test](https://github.com/xtyxtyx/minio-dart/workflows/Dart/badge.svg)

![Pub Version](https://img.shields.io/pub/v/minio)


## API

| Bucket operations       | Object operations        | Presigned operations | Bucket Policy & Notification operations |
|-------------------------|--------------------------|----------------------|-----------------------------------------|
| [makeBucket]            | [getObject]              | [presignedUrl]       | [getBucketNotification]                 |
| [listBuckets]           | [getPartialObject]       | [presignedGetObject] | [setBucketNotification]                 |
| [bucketExists]          | [fGetObject]             | [presignedPutObject] | [removeAllBucketNotification]           |
| [removeBucket]          | [putObject]              | [presignedPostPolicy]| [listenBucketNotification]              |
| [listObjects]           | [fPutObject]             |                      | [getBucketPolicy]                       |
| [listObjectsV2]         | [copyObject]             |                      | [setBucketPolicy]                       |
| [listIncompleteUploads] | [statObject]             |                      |                                         |
|                         | [removeObject]           |                      |                                         |
|                         | [removeObjects]          |                      |                                         |
|                         | [removeIncompleteUpload] |                      |                                         |


## Usage

### Initialize MinIO Client

**MinIO**

```dart
final minio = Minio(
  endPoint: 'play.min.io',
  accessKey: 'Q3AM3UQ867SPQQA43P2F',
  secretKey: 'zuf+tfteSlswRu7BJ86wekitnifILbZam1KYY3TG',
);
```

**AWS S3**

```dart
final minio = Minio(
  endPoint: 's3.amazonaws.com',
  accessKey: 'YOUR-ACCESSKEYID',
  secretKey: 'YOUR-SECRETACCESSKEY',
);
```

**File upload**
```dart
import 'package:minio/io.dart';
import 'package:minio/minio.dart';

void main() async {
  final minio = Minio(
    endPoint: 'play.min.io',
    accessKey: 'Q3AM3UQ867SPQQA43P2F',
    secretKey: 'zuf+tfteSlswRu7BJ86wekitnifILbZam1KYY3TG',
  );

  await minio.fPutObject('mybucket', 'myobject', 'path/to/file');
}
```

For complete example, see: [example]

> To use `fPutObject()` and `fGetObject`, you have to `import 'package:minio/io.dart';`

## Features and bugs

Please file feature requests and bugs at the [issue tracker][tracker].

Contributions to this repository are welcome.