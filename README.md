[![Documentation Status](https://readthedocs.org/projects/py-ipv8/badge/?version=latest)](https://py-ipv8.readthedocs.io/)

**Linux**: [![](http://jenkins-ci.tribler.org/job/ipv8/job/test_ipv8_linux/badge/icon)](http://jenkins-ci.tribler.org/job/ipv8/job/test_ipv8_linux/) **Windows**: [![](http://jenkins-ci.tribler.org/job/ipv8/job/test_ipv8_windows/badge/icon)](http://jenkins-ci.tribler.org/job/ipv8/job/test_ipv8_windows/) **Mac**: [![](http://jenkins-ci.tribler.org/job/ipv8/job/test_ipv8_mac/badge/icon)](http://jenkins-ci.tribler.org/job/ipv8/job/test_ipv8_mac/)

## What is IPv8 ?

IPv8 aims to provide authenticated communication with privacy.
The design principle is to enable communication between public key pairs: IP addresses and physical network attachment points are abstracted away.
This Python 2/3 package is an amalgamation of peer-to-peer communication functionality from [Dispersy](https://github.com/Tribler/dispersy) and [Tribler](https://github.com/Tribler/tribler), developed over the last 13 years by students and employees of the Delft University of Technology.
The IPv8 library allows you to easily create network overlays on which to build your own applications.

### IPv8 Objectives

- **Authentication**. We offer mutual authentication using strong cryptography. During an IPv8 communication session, both parties can be sure of the other party’s identity. IPv8 users are identified by their public key. The initial key exchange is designed so that secrets are never transmitted across the Internet, not even in encrypted form. We use a standard challenge/response protocol with protection against spoofing, man-in-the-middle, and replay attacks.
- **Privacy**. IPv8 is specifically designed for strong privacy protection and end-to-end encryption with perfect forward secrecy. We enhanced the industry standard onion routing protocol, Tor, for usage in a trustless environment (e.g. no trusted central directory servers).
- **No infrastructure dependency**. Everybody is equal in the world of IPv8. No central web server, discovery server, or support foundation is needed.
- **NAT traversal**. IPv8 can establish direct communication in difficult network situations. This includes connecting people behind a NAT or firewall.   IPv8 includes a single simple and effective NAT traversal technique: UDP hole-punching. This is essential when offering privacy without infrastructure and consumer-grade donated resources.
- **Trust**. You can enhance your security if you tell IPv8 which people you know and trust. It tries to build a web-of-trust automatically.

### Dependencies
The dependencies for IPv8 are collected in the `requirements.txt` file and can be installed using `pip`:

```
pip install --upgrade -r requirements.txt
```

On Windows or MacOS you will need to install `Libsodium` separately, as explained [here](https://github.com/Tribler/py-ipv8/blob/master/doc/preliminaries/install_libsodium.rst). 

### Tests
The test suite can run without any external packages, but the `nosetests` package is recommended (`pip install nose`).
The test suite will automatically detect your back-end when running the tests.
Running tests can be done (**on UNIX**) by running:

```
bash run_all_tests_unix.sh
```

On Windows you can run `run_all_tests_windows.bat` from the Command Prompt (`cmd.exe`).
Running code coverage requires the `coverage` package (`pip install coverage`).
A coverage report can be generated by running:

```
python create_test_coverage_report.py
```

### Getting started
IPv8 can be used as a library or as a service. It is easiest to start off with the service, which has been provided [here](https://github.com/Tribler/py-ipv8/blob/master/ipv8_service.py) (see the [configuration file](https://py-ipv8.readthedocs.io/en/latest/reference/configuration/) for invocation options).
This file will load the IPv8 stack for *signed messaging*, *anonymous messaging*, *attribute attestation*, *public service discovery*, *peer discovery* and *peer keep-alive*.
You can start creating your first network overlay by following [the overlay creation tutorial](https://py-ipv8.readthedocs.io/en/latest/basics/overlay_tutorial/).

Additional documentation is also available for the [TrustChain](https://py-ipv8.readthedocs.io/en/latest/further-reading/trustchain/) and [anonymous overlay](https://py-ipv8.readthedocs.io/en/latest/further-reading/anonymization/) provided in IPv8.

