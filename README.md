# task_no3_part_01

# Kafka SSL Authentication Setup Guide

This guide describes the steps to configure SSL for a Kafka cluster with three nodes. The process involves creating a Certificate Authority (CA), generating keystores and truststores, and signing certificates for Kafka brokers.

## Prerequisites
- Java JDK (`keytool` command is part of the JDK).
- OpenSSL installed for certificate creation and signing.
- Kafka and Zookeeper installed and running.

### Step 1: Create Your Own Certificate Authority (CA)
Generate a new CA key and certificate:

```bash
openssl req -new -x509 -days 365 -keyout ca-key -out ca-cert -subj "/C=DE/ST=NRW/L=MS/O=juplo/OU=kafka/CN=Root-CA" -passout pass:kafka-broker
