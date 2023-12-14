# challenge-lab

Installation
import os
! pip3 install --user --upgrade google-cloud-aiplatform
Requirement already satisfied: google-cloud-aiplatform in /opt/conda/lib/python3.10/site-packages (1.37.0)
Collecting google-cloud-aiplatform
  Downloading google_cloud_aiplatform-1.38.1-py2.py3-none-any.whl.metadata (27 kB)
Requirement already satisfied: google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.34.0)
Requirement already satisfied: proto-plus<2.0.0dev,>=1.22.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (1.23.0)
Requirement already satisfied: protobuf!=3.20.0,!=3.20.1,!=4.21.0,!=4.21.1,!=4.21.2,!=4.21.3,!=4.21.4,!=4.21.5,<5.0.0dev,>=3.19.5 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (3.19.6)
Requirement already satisfied: packaging>=14.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (23.2)
Requirement already satisfied: google-cloud-storage<3.0.0dev,>=1.32.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (2.13.0)
Requirement already satisfied: google-cloud-bigquery<4.0.0dev,>=1.15.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (3.13.0)
Requirement already satisfied: google-cloud-resource-manager<3.0.0dev,>=1.3.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (1.11.0)
Requirement already satisfied: shapely<3.0.0dev in /opt/conda/lib/python3.10/site-packages (from google-cloud-aiplatform) (2.0.2)
Requirement already satisfied: googleapis-common-protos<2.0dev,>=1.56.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.62.0)
Requirement already satisfied: google-auth<3.0dev,>=1.25.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (2.25.2)
Requirement already satisfied: requests<3.0.0dev,>=2.18.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (2.31.0)
Requirement already satisfied: grpcio<2.0dev,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.48.1)
Requirement already satisfied: grpcio-status<2.0dev,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.48.1)
Requirement already satisfied: google-cloud-core<3.0.0dev,>=1.6.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-bigquery<4.0.0dev,>=1.15.0->google-cloud-aiplatform) (2.4.1)
Requirement already satisfied: google-resumable-media<3.0dev,>=0.6.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-bigquery<4.0.0dev,>=1.15.0->google-cloud-aiplatform) (2.6.0)
Requirement already satisfied: python-dateutil<3.0dev,>=2.7.2 in /opt/conda/lib/python3.10/site-packages (from google-cloud-bigquery<4.0.0dev,>=1.15.0->google-cloud-aiplatform) (2.8.2)
Requirement already satisfied: grpc-google-iam-v1<1.0.0dev,>=0.12.4 in /opt/conda/lib/python3.10/site-packages (from google-cloud-resource-manager<3.0.0dev,>=1.3.3->google-cloud-aiplatform) (0.12.7)
Requirement already satisfied: google-crc32c<2.0dev,>=1.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.5.0)
Requirement already satisfied: numpy>=1.14 in /opt/conda/lib/python3.10/site-packages (from shapely<3.0.0dev->google-cloud-aiplatform) (1.24.4)
Requirement already satisfied: cachetools<6.0,>=2.0.0 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (4.2.4)
Requirement already satisfied: pyasn1-modules>=0.2.1 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (0.3.0)
Requirement already satisfied: rsa<5,>=3.1.4 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (4.9)
Requirement already satisfied: six>=1.5.2 in /opt/conda/lib/python3.10/site-packages (from grpcio<2.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.16.0)
Requirement already satisfied: charset-normalizer<4,>=2 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (3.3.2)
Requirement already satisfied: idna<4,>=2.5 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (3.6)
Requirement already satisfied: urllib3<3,>=1.21.1 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (1.26.18)
Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (2023.11.17)
Requirement already satisfied: pyasn1<0.6.0,>=0.4.6 in /opt/conda/lib/python3.10/site-packages (from pyasn1-modules>=0.2.1->google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.32.0->google-cloud-aiplatform) (0.5.1)
Downloading google_cloud_aiplatform-1.38.1-py2.py3-none-any.whl (3.4 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.4/3.4 MB 16.9 MB/s eta 0:00:00a 0:00:01
Installing collected packages: google-cloud-aiplatform
  WARNING: The script tb-gcp-uploader is installed in '/home/jupyter/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
Successfully installed google-cloud-aiplatform-1.38.1
Install the latest GA version of google-cloud-storage library.

! pip3 install --user --upgrade google-cloud-storage
Requirement already satisfied: google-cloud-storage in /opt/conda/lib/python3.10/site-packages (2.13.0)
Collecting google-cloud-storage
  Downloading google_cloud_storage-2.14.0-py2.py3-none-any.whl.metadata (6.1 kB)
Requirement already satisfied: google-auth<3.0dev,>=2.23.3 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage) (2.25.2)
Requirement already satisfied: google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.0,<3.0.0dev,>=1.31.5 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage) (1.34.0)
Requirement already satisfied: google-cloud-core<3.0dev,>=2.3.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage) (2.4.1)
Requirement already satisfied: google-resumable-media>=2.6.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage) (2.6.0)
Requirement already satisfied: requests<3.0.0dev,>=2.18.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage) (2.31.0)
Requirement already satisfied: google-crc32c<2.0dev,>=1.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-storage) (1.5.0)
Requirement already satisfied: googleapis-common-protos<2.0dev,>=1.56.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.0,<3.0.0dev,>=1.31.5->google-cloud-storage) (1.62.0)
Requirement already satisfied: protobuf!=3.20.0,!=3.20.1,!=4.21.0,!=4.21.1,!=4.21.2,!=4.21.3,!=4.21.4,!=4.21.5,<4.0.0dev,>=3.19.5 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.0,<3.0.0dev,>=1.31.5->google-cloud-storage) (3.19.6)
Requirement already satisfied: cachetools<6.0,>=2.0.0 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=2.23.3->google-cloud-storage) (4.2.4)
Requirement already satisfied: pyasn1-modules>=0.2.1 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=2.23.3->google-cloud-storage) (0.3.0)
Requirement already satisfied: rsa<5,>=3.1.4 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=2.23.3->google-cloud-storage) (4.9)
Requirement already satisfied: charset-normalizer<4,>=2 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-cloud-storage) (3.3.2)
Requirement already satisfied: idna<4,>=2.5 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-cloud-storage) (3.6)
Requirement already satisfied: urllib3<3,>=1.21.1 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-cloud-storage) (1.26.18)
Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-cloud-storage) (2023.11.17)
Requirement already satisfied: pyasn1<0.6.0,>=0.4.6 in /opt/conda/lib/python3.10/site-packages (from pyasn1-modules>=0.2.1->google-auth<3.0dev,>=2.23.3->google-cloud-storage) (0.5.1)
Downloading google_cloud_storage-2.14.0-py2.py3-none-any.whl (121 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 121.6/121.6 kB 1.4 MB/s eta 0:00:00a 0:00:01m
Installing collected packages: google-cloud-storage
Successfully installed google-cloud-storage-2.14.0
Install the latest version of google-cloud-logging library.

! pip3 install --user --upgrade google-cloud-logging
Collecting google-cloud-logging
  Downloading google_cloud_logging-3.9.0-py2.py3-none-any.whl.metadata (4.8 kB)
Requirement already satisfied: google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (1.34.0)
Collecting google-cloud-appengine-logging<2.0.0dev,>=0.1.0 (from google-cloud-logging)
  Downloading google_cloud_appengine_logging-1.4.0-py2.py3-none-any.whl.metadata (5.3 kB)
Collecting google-cloud-audit-log<1.0.0dev,>=0.1.0 (from google-cloud-logging)
  Downloading google_cloud_audit_log-0.2.5-py2.py3-none-any.whl (12 kB)
Requirement already satisfied: google-cloud-core<3.0.0dev,>=2.0.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-logging) (2.4.1)
Requirement already satisfied: grpc-google-iam-v1<1.0.0dev,>=0.12.4 in /opt/conda/lib/python3.10/site-packages (from google-cloud-logging) (0.12.7)
Requirement already satisfied: proto-plus<2.0.0dev,>=1.22.0 in /opt/conda/lib/python3.10/site-packages (from google-cloud-logging) (1.23.0)
Requirement already satisfied: protobuf!=3.20.0,!=3.20.1,!=4.21.0,!=4.21.1,!=4.21.2,!=4.21.3,!=4.21.4,!=4.21.5,<5.0.0dev,>=3.19.5 in /opt/conda/lib/python3.10/site-packages (from google-cloud-logging) (3.19.6)
Requirement already satisfied: googleapis-common-protos<2.0dev,>=1.56.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (1.62.0)
Requirement already satisfied: google-auth<3.0dev,>=1.25.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (2.25.2)
Requirement already satisfied: requests<3.0.0dev,>=2.18.0 in /opt/conda/lib/python3.10/site-packages (from google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (2.31.0)
Requirement already satisfied: grpcio<2.0dev,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (1.48.1)
Requirement already satisfied: grpcio-status<2.0dev,>=1.33.2 in /opt/conda/lib/python3.10/site-packages (from google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (1.48.1)
Requirement already satisfied: cachetools<6.0,>=2.0.0 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (4.2.4)
Requirement already satisfied: pyasn1-modules>=0.2.1 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (0.3.0)
Requirement already satisfied: rsa<5,>=3.1.4 in /opt/conda/lib/python3.10/site-packages (from google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (4.9)
Requirement already satisfied: six>=1.5.2 in /opt/conda/lib/python3.10/site-packages (from grpcio<2.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (1.16.0)
Requirement already satisfied: charset-normalizer<4,>=2 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (3.3.2)
Requirement already satisfied: idna<4,>=2.5 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (3.6)
Requirement already satisfied: urllib3<3,>=1.21.1 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (1.26.18)
Requirement already satisfied: certifi>=2017.4.17 in /opt/conda/lib/python3.10/site-packages (from requests<3.0.0dev,>=2.18.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (2023.11.17)
Requirement already satisfied: pyasn1<0.6.0,>=0.4.6 in /opt/conda/lib/python3.10/site-packages (from pyasn1-modules>=0.2.1->google-auth<3.0dev,>=1.25.0->google-api-core!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-api-core[grpc]!=2.0.*,!=2.1.*,!=2.2.*,!=2.3.*,!=2.4.*,!=2.5.*,!=2.6.*,!=2.7.*,<3.0.0dev,>=1.33.2->google-cloud-logging) (0.5.1)
Downloading google_cloud_logging-3.9.0-py2.py3-none-any.whl (207 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 207.3/207.3 kB 2.1 MB/s eta 0:00:00a 0:00:01m
Downloading google_cloud_appengine_logging-1.4.0-py2.py3-none-any.whl (15 kB)
Installing collected packages: google-cloud-audit-log, google-cloud-appengine-logging, google-cloud-logging
Successfully installed google-cloud-appengine-logging-1.4.0 google-cloud-audit-log-0.2.5 google-cloud-logging-3.9.0
Downgrade protobuf for tensorflow datasets compatibility

! pip3 install --user protobuf==3.19.*
Requirement already satisfied: protobuf==3.19.* in /opt/conda/lib/python3.10/site-packages (3.19.6)
Install the pillow library for loading images.

! pip3 install --user --upgrade pillow
Requirement already satisfied: pillow in /opt/conda/lib/python3.10/site-packages (10.1.0)
Install the numpy library for manipulation of image data.

! pip3 install --user --upgrade numpy
Requirement already satisfied: numpy in /opt/conda/lib/python3.10/site-packages (1.24.4)
Collecting numpy
  Downloading numpy-1.26.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl.metadata (61 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 61.2/61.2 kB 1.2 MB/s eta 0:00:00a 0:00:01
Downloading numpy-1.26.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (18.2 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 18.2/18.2 MB 43.6 MB/s eta 0:00:0000:0100:01
Installing collected packages: numpy
  WARNING: The script f2py is installed in '/home/jupyter/.local/bin' which is not on PATH.
  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed. This behaviour is the source of the following dependency conflicts.
apache-beam 2.46.0 requires numpy<1.25.0,>=1.14.3, but you have numpy 1.26.2 which is incompatible.
ydata-profiling 4.6.0 requires numpy<1.26,>=1.16.0, but you have numpy 1.26.2 which is incompatible.
Successfully installed numpy-1.26.2
You can safely ignore errors during the numpy installation.

Restart the kernel
Once you've installed everything, you need to restart the notebook kernel so it can find the packages.

import os
​
if not os.getenv("IS_TESTING"):
    # Automatically restart kernel after installs
    import IPython
​
    app = IPython.Application.instance()
    app.kernel.do_shutdown(True)
Set your project ID
If you don't know your project ID, you may be able to get your project ID using gcloud.

import os
​
# Retrieve and set PROJECT_ID environment variables.
# TODO: fill in PROJECT_ID.
​
if not os.getenv("IS_TESTING"):
    # Get your Google Cloud project ID from gcloud
    PROJECT_ID = "qwiklabs-gcp-03-a61679897bda"
PROJECT_ID
'qwiklabs-gcp-03-a61679897bda'
Timestamp
If you are in a live tutorial session, you might be using a shared test account or project. To avoid name collisions between users on resources created, you create a timestamp for each instance session, and append it onto the name of resources you create in this tutorial.

from datetime import datetime
​
TIMESTAMP = datetime.now().strftime("%Y%m%d%H%M%S")
Create a Cloud Storage bucket
The following steps are required, regardless of your notebook environment.

When you submit a training job using the Cloud SDK, you upload a Python package containing your training code to a Cloud Storage bucket. Vertex AI runs the code from this package. In this tutorial, Vertex AI also saves the trained model that results from your job in the same bucket. Using this model artifact, you can then create Vertex AI model and endpoint resources in order to serve online predictions.

Set the name of your Cloud Storage bucket below. It must be unique across all Cloud Storage buckets.

You may also change the REGION variable, which is used for operations throughout the rest of this notebook. Make sure to choose a region where Vertex AI services are available. You may not use a Multi-Regional Storage bucket for training with Vertex AI.

REGION = "us-central1"  # @param {type:"string"}
# TODO: Create a globally unique Google Cloud Storage bucket name for artifact storage.
# HINT: Start the name with gs://
BUCKET_NAME = "gs://qwiklabs-gcp-03-a61679897bda"
! gsutil mb -l $REGION $BUCKET_NAME
Creating gs://qwiklabs-gcp-03-a61679897bda/...
ServiceException: 409 A Cloud Storage bucket named 'qwiklabs-gcp-03-a61679897bda' already exists. Try another name. Bucket names must be globally unique across all Google Cloud projects, including those outside of your organization.
Set up variables
Next, set up some variables used throughout the tutorial.

Import Vertex SDK for Python
Import the Vertex SDK for Python into your Python environment and initialize it.

import os
import sys
​
from google.cloud import aiplatform
from google.cloud.aiplatform import gapic as aip
​
aiplatform.init(project=PROJECT_ID, location=REGION, staging_bucket=BUCKET_NAME)
Set hardware accelerators
Here to run a container image on a CPU, we set the variables TRAIN_GPU/TRAIN_NGPU and DEPLOY_GPU/DEPLOY_NGPU to (None, None) since this notebook is meant to be run in a Qwiklab environment where GPUs cannot be provisioned.

Note: If you happen to be running this notebook from your personal GCP account, set the variables TRAIN_GPU/TRAIN_NGPU and DEPLOY_GPU/DEPLOY_NGPU to use a container image supporting a GPU and the number of GPUs allocated to the virtual machine (VM) instance. For example, to use a GPU container image with 4 Nvidia Tesla K80 GPUs allocated to each VM, you would specify:

(aip.AcceleratorType.NVIDIA_TESLA_K80, 4)
See the locations where accelerators are available.

TRAIN_GPU, TRAIN_NGPU = (None, None)
DEPLOY_GPU, DEPLOY_NGPU = (None, None)
Set pre-built containers
There are two ways you can train a custom model using a container image:

Use a Google Cloud prebuilt container. If you use a prebuilt container, you will additionally specify a Python package to install into the container image. This Python package contains your code for training a custom model.

Use your own custom container image. If you use your own container, the container needs to contain your code for training a custom model.

Here you will use pre-built containers provided by Vertex AI to run training and prediction.

For the latest list, see Pre-built containers for training and Pre-built containers for prediction

TRAIN_VERSION = "tf-cpu.2-8"
DEPLOY_VERSION = "tf2-cpu.2-8"
​
TRAIN_IMAGE = "us-docker.pkg.dev/vertex-ai/training/{}:latest".format(TRAIN_VERSION)
DEPLOY_IMAGE = "us-docker.pkg.dev/vertex-ai/prediction/{}:latest".format(DEPLOY_VERSION)
​
print("Training:", TRAIN_IMAGE, TRAIN_GPU, TRAIN_NGPU)
print("Deployment:", DEPLOY_IMAGE, DEPLOY_GPU, DEPLOY_NGPU)
Training: us-docker.pkg.dev/vertex-ai/training/tf-cpu.2-8:latest None None
Deployment: us-docker.pkg.dev/vertex-ai/prediction/tf2-cpu.2-8:latest None None
Set machine types
Next, set the machine types to use for training and prediction.

Set the variables TRAIN_COMPUTE and DEPLOY_COMPUTE to configure your compute resources for training and prediction.
machine type
n1-standard: 3.75GB of memory per vCPU
n1-highmem: 6.5GB of memory per vCPU
n1-highcpu: 0.9 GB of memory per vCPU
vCPUs: number of [2, 4, 8, 16, 32, 64, 96 ]
Note: The following is not supported for training:

standard: 2 vCPUs
highcpu: 2, 4 and 8 vCPUs
Note: You may also use n2 and e2 machine types for training and deployment, but they do not support GPUs.

MACHINE_TYPE = "n1-standard"
​
VCPU = "4"
TRAIN_COMPUTE = MACHINE_TYPE + "-" + VCPU
print("Train machine type", TRAIN_COMPUTE)
​
MACHINE_TYPE = "n1-standard"
​
VCPU = "4"
DEPLOY_COMPUTE = MACHINE_TYPE + "-" + VCPU
print("Deploy machine type", DEPLOY_COMPUTE)
Train machine type n1-standard-4
Deploy machine type n1-standard-4
Training script
In the next cell, you will write the contents of the training script, task.py.

%%writefile task.py
# Training kmnist using CNN
​
import tensorflow_datasets as tfds
import tensorflow as tf
from tensorflow.python.client import device_lib
import argparse
import os
import sys
tfds.disable_progress_bar()
​
parser = argparse.ArgumentParser()
​
parser.add_argument('--epochs', dest='epochs',
                    default=10, type=int,
                    help='Number of epochs.')
​
args = parser.parse_args()
​
print('Python Version = {}'.format(sys.version))
print('TensorFlow Version = {}'.format(tf.__version__))
print('TF_CONFIG = {}'.format(os.environ.get('TF_CONFIG', 'Not found')))
print('DEVICES', device_lib.list_local_devices())
​
# Define batch size
BATCH_SIZE = 32
​
# Load the dataset
datasets, info = tfds.load('kmnist', with_info=True, as_supervised=True)
​
# Normalize and batch process the dataset
ds_train = datasets['train'].map(lambda x, y: (tf.cast(x, tf.float32)/255.0, y)).batch(BATCH_SIZE)
​
​
# Build the Convolutional Neural Network
model = tf.keras.models.Sequential([                               
      tf.keras.layers.Conv2D(16, (3,3), activation=tf.nn.relu, input_shape=(28, 28, 1), padding = "same"),
      tf.keras.layers.MaxPooling2D(2,2),
      tf.keras.layers.Conv2D(16, (3,3), activation=tf.nn.relu, padding = "same"),
      tf.keras.layers.MaxPooling2D(2,2),
      tf.keras.layers.Flatten(),
      tf.keras.layers.Dense(128, activation=tf.nn.relu),
      # TODO: Write the last layer.
      # Hint: KMNIST has 10 output classes.
      
    ])
​
model.compile(optimizer = tf.keras.optimizers.Adam(),
      loss = tf.keras.losses.SparseCategoricalCrossentropy(),
      metrics=[tf.keras.metrics.SparseCategoricalAccuracy()])
​
​
​
# Train and save the model
​
MODEL_DIR = os.getenv("AIP_MODEL_DIR")
​
model.fit(ds_train, epochs=args.epochs)
​
# TODO: Save your CNN classifier. 
# Hint: Save it to MODEL_DIR.
model.save(MODEL_DIR)
Writing task.py
Define the command args for the training script
Prepare the command-line arguments to pass to your training script.

args: The command line arguments to pass to the corresponding Python module. In this example, they will be:
"--epochs=" + EPOCHS: The number of epochs for training.
JOB_NAME = "custom_job_" + TIMESTAMP
MODEL_DIR = "{}/{}".format(BUCKET_NAME, JOB_NAME)
​
EPOCHS = 5
​
CMDARGS = [
    "--epochs=" + str(EPOCHS),
]
Train the model
Define your custom training job on Vertex AI.

    
job = aiplatform.CustomTrainingJob(
    display_name=JOB_NAME,
    requirements=["tensorflow_datasets==4.6.0"],
    # TODO: fill in the remaining arguments for the CustomTrainingJob function.
    script_path="task.py",
    container_uri=TRAIN_IMAGE,
    model_serving_container_image_uri=DEPLOY_IMAGE,
)
​
MODEL_DISPLAY_NAME = "kmnist-" + TIMESTAMP
​
# Start the training
model = job.run(
    model_display_name=MODEL_DISPLAY_NAME,
    replica_count=1,
    accelerator_count=0,
    # TODO: fill in the remaining arguments to run the custom training job function.
    args=CMDARGS,
    machine_type=TRAIN_COMPUTE,
)
Training script copied to:
gs://qwiklabs-gcp-03-a61679897bda/aiplatform-2023-12-14-12:24:49.941-aiplatform_custom_trainer_script-0.1.tar.gz.
Training Output directory:
gs://qwiklabs-gcp-03-a61679897bda/aiplatform-custom-training-2023-12-14-12:24:50.060 
View Training:
https://console.cloud.google.com/ai/platform/locations/us-central1/training/614738256759619584?project=170000564228
CustomTrainingJob projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584 current state:
PipelineState.PIPELINE_STATE_PENDING
CustomTrainingJob projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584 current state:
PipelineState.PIPELINE_STATE_RUNNING
View backing custom job:
https://console.cloud.google.com/ai/platform/locations/us-central1/training/9064317990450757632?project=170000564228
CustomTrainingJob projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584 current state:
PipelineState.PIPELINE_STATE_RUNNING
CustomTrainingJob projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584 current state:
PipelineState.PIPELINE_STATE_RUNNING
CustomTrainingJob projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584 current state:
PipelineState.PIPELINE_STATE_RUNNING
CustomTrainingJob projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584 current state:
PipelineState.PIPELINE_STATE_RUNNING
CustomTrainingJob run completed. Resource name: projects/170000564228/locations/us-central1/trainingPipelines/614738256759619584
Model available at projects/170000564228/locations/us-central1/models/5582156762544340992
Deploy the model
Before you use your model to make predictions, you need to deploy it to an Endpoint. You can do this by calling the deploy function on the Model resource.

DEPLOYED_NAME = "kmnist_deployed-" + TIMESTAMP
​
TRAFFIC_SPLIT = {"0": 100}
​
MIN_NODES = 1
MAX_NODES = 1
​
endpoint = model.deploy(
        deployed_model_display_name=DEPLOYED_NAME,
        accelerator_type=None,
        accelerator_count=0,
        # TODO: fill in the remaining arguments to deploy the model to an endpoint.
        traffic_split=TRAFFIC_SPLIT,
        machine_type=DEPLOY_COMPUTE,
        min_replica_count=MIN_NODES,
        max_replica_count=MAX_NODES,
    )
Creating Endpoint
INFO:google.cloud.aiplatform.models:Creating Endpoint
Create Endpoint backing LRO: projects/170000564228/locations/us-central1/endpoints/7922264952126046208/operations/1648659892770177024
INFO:google.cloud.aiplatform.models:Create Endpoint backing LRO: projects/170000564228/locations/us-central1/endpoints/7922264952126046208/operations/1648659892770177024
Endpoint created. Resource name: projects/170000564228/locations/us-central1/endpoints/7922264952126046208
INFO:google.cloud.aiplatform.models:Endpoint created. Resource name: projects/170000564228/locations/us-central1/endpoints/7922264952126046208
To use this Endpoint in another session:
INFO:google.cloud.aiplatform.models:To use this Endpoint in another session:
endpoint = aiplatform.Endpoint('projects/170000564228/locations/us-central1/endpoints/7922264952126046208')
INFO:google.cloud.aiplatform.models:endpoint = aiplatform.Endpoint('projects/170000564228/locations/us-central1/endpoints/7922264952126046208')
Deploying model to Endpoint : projects/170000564228/locations/us-central1/endpoints/7922264952126046208
INFO:google.cloud.aiplatform.models:Deploying model to Endpoint : projects/170000564228/locations/us-central1/endpoints/7922264952126046208
Deploy Endpoint model backing LRO: projects/170000564228/locations/us-central1/endpoints/7922264952126046208/operations/7823094981895127040
INFO:google.cloud.aiplatform.models:Deploy Endpoint model backing LRO: projects/170000564228/locations/us-central1/endpoints/7922264952126046208/operations/7823094981895127040
Endpoint model deployed. Resource name: projects/170000564228/locations/us-central1/endpoints/7922264952126046208
INFO:google.cloud.aiplatform.models:Endpoint model deployed. Resource name: projects/170000564228/locations/us-central1/endpoints/7922264952126046208
Make an online prediction request
Send an online prediction request to your deployed model.

import tensorflow_datasets as tfds
import numpy as np
​
tfds.disable_progress_bar()
datasets, info = tfds.load('kmnist', batch_size=-1, with_info=True, as_supervised=True)
​
test_dataset = datasets['test']
x_test, y_test = tfds.as_numpy(test_dataset)
​
# Normalize (rescale) the pixel data by dividing each pixel by 255. 
x_test = x_test.astype('float32') / 255.
x_test.shape, y_test.shape
((10000, 28, 28, 1), (10000,))
#@title Pick the number of test images
NUM_TEST_IMAGES = 20 #@param {type:"slider", min:1, max:20, step:1}
x_test, y_test = x_test[:NUM_TEST_IMAGES], y_test[:NUM_TEST_IMAGES]
Send the prediction request
Logging module added to log the prediction result

# Import and configure logging
from google.cloud import logging
logging_client = logging.Client()
logger = logging_client.logger('challenge-notebook')
Now that you have test images, you can use them to send a prediction request.

# TODO: use your Endpoint to return prediction for your x_test.
​
predictions = endpoint.predict(instances=x_test.tolist())
​
y_predicted = np.argmax(predictions.predictions, axis=1)
​
correct = sum(y_predicted == np.array(y_test.tolist()))
total = len(y_predicted)
​
logger.log_text(str(correct/total))
​
print(
    f"Correct predictions = {correct}, Total predictions = {total}, Accuracy = {correct/total}"
)
Correct predictions = 3, Total predictions = 20, Accuracy = 0.15
​
​
​

Simple
1
1

master
Python 3 (Local) | Idle
2
cnn_challenge_lab.ipynb
Ln 1, Col 1
Mode: Command
