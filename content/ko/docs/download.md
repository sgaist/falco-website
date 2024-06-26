---
exclude_search: true
title: 다운로드
description: 공식 지원 팔코 아티팩트
weight: 2
---

## 다운로드

팔코 프로젝트 커뮤니티는 다운로드와 실행 방법을 두 가지만 지원한다.

 - Linux 호스트에서 직접 팔코 실행하기
 - 드라이버가 설치된 호스트 상의 컨테이너에서 팔코 사용자 공간 프로그램(userspace program) 실행하기

다음은 두 가지 아티팩트에 대한 내용이다.

### 리눅스를 위한 다운로드 {#packages}

|        | development                                                                                                                 | stable                                                                                                              |
|--------|-----------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| rpm    | [![rpm-dev](https://img.shields.io/badge/dynamic/xml?color=%2300aec7&style=flat-square&label=Falco&query=substring-before%28substring-after%28%28%2F%2A%5Bname%28%29%3D%27ListBucketResult%27%5D%2F%2A%5Bname%28%29%3D%27Contents%27%5D%29%5Blast%28%29%5D%2F%2A%5Bname%28%29%3D%27Key%27%5D%2C%22falco-%22%29%2C%22.asc%22%29&url=https%3A%2F%2Ffalco-distribution.s3-eu-west-1.amazonaws.com%2F%3Fprefix%3Dpackages%2Frpm-dev%2Ffalco-)][1] | [![rpm](https://img.shields.io/badge/dynamic/xml?color=%2300aec7&style=flat-square&label=Falco&query=substring-before%28substring-after%28%28%2F%2A%5Bname%28%29%3D%27ListBucketResult%27%5D%2F%2A%5Bname%28%29%3D%27Contents%27%5D%29%5Blast%28%29%5D%2F%2A%5Bname%28%29%3D%27Key%27%5D%2C%22falco-%22%29%2C%22.asc%22%29&url=https%3A%2F%2Ffalco-distribution.s3-eu-west-1.amazonaws.com%2F%3Fprefix%3Dpackages%2Frpm%2Ffalco-)][2] |
| deb    | [![deb-dev](https://img.shields.io/badge/dynamic/xml?color=%2300aec7&style=flat-square&label=Falco&query=substring-before%28substring-after%28%28%2F%2A%5Bname%28%29%3D%27ListBucketResult%27%5D%2F%2A%5Bname%28%29%3D%27Contents%27%5D%29%5Blast%28%29%5D%2F%2A%5Bname%28%29%3D%27Key%27%5D%2C%22falco-%22%29%2C%22.asc%22%29&url=https%3A%2F%2Ffalco-distribution.s3-eu-west-1.amazonaws.com%2F%3Fprefix%3Dpackages%2Fdeb-dev%2Fstable%2Ffalco-)][3] | [![deb](https://img.shields.io/badge/dynamic/xml?color=%2300aec7&style=flat-square&label=Falco&query=substring-before%28substring-after%28%28%2F%2A%5Bname%28%29%3D%27ListBucketResult%27%5D%2F%2A%5Bname%28%29%3D%27Contents%27%5D%29%5Blast%28%29%5D%2F%2A%5Bname%28%29%3D%27Key%27%5D%2C%22falco-%22%29%2C%22.asc%22%29&url=https%3A%2F%2Ffalco-distribution.s3-eu-west-1.amazonaws.com%2F%3Fprefix%3Dpackages%2Fdeb%2Fstable%2Ffalco-)][4] |
| binary | [![bin-dev](https://img.shields.io/badge/dynamic/xml?color=%2300aec7&style=flat-square&label=Falco&query=substring-after%28%28%2F%2A%5Bname%28%29%3D%27ListBucketResult%27%5D%2F%2A%5Bname%28%29%3D%27Contents%27%5D%29%5Blast%28%29%5D%2F%2A%5Bname%28%29%3D%27Key%27%5D%2C%20%22falco-%22%29&url=https%3A%2F%2Ffalco-distribution.s3-eu-west-1.amazonaws.com%2F%3Fprefix%3Dpackages%2Fbin-dev%2Fx86_64%2Ffalco-)][5] | [![bin](https://img.shields.io/badge/dynamic/xml?color=%2300aec7&style=flat-square&label=Falco&query=substring-after%28%28%2F%2A%5Bname%28%29%3D%27ListBucketResult%27%5D%2F%2A%5Bname%28%29%3D%27Contents%27%5D%29%5Blast%28%29%5D%2F%2A%5Bname%28%29%3D%27Key%27%5D%2C%20%22falco-%22%29&url=https%3A%2F%2Ffalco-distribution.s3-eu-west-1.amazonaws.com%2F%3Fprefix%3Dpackages%2Fbin%2Fx86_64%2Ffalco-)][6] |


사용 가능한 전체 아티팩트 목록은 [여기](https://download.falco.org/?prefix=packages)에서 확인할 수 있다.

---

### 컨테이너 이미지 다운로드 {#images}

{{% pageinfo color="primary" %}}

팔코는 실행 중인 시스템 호출 정보를 얻기 위해 호스트 시스템에 드라이버를 설치해야 한다.

권장하는 방법은 위에서 명시한 네이티브 아티팩트로 드라이버를 설치하거나, `falcosecurity/falco-driver-loader` 이미지를 임시로 특권을 이용해(as privileged) 실행한 다음 `falcosecurity/falco-no-driver` 이미지를 사용하는 것이다.

자세한 내용은 [Docker 섹션 내에서 실행](https://falco.org/docs/getting-started/running/#docker)을 참고한다.

{{% /pageinfo %}}

|tag | pull command | description |
|----|----------|-----------------|
|[latest](https://hub.docker.com/r/falcosecurity/falco-no-driver/tags)| `docker pull falcosecurity/falco-no-driver:latest` | 최신 버전 |
|[*version*](https://hub.docker.com/r/falcosecurity/falco-no-driver/tags)| `docker pull falcosecurity/falco-no-driver:<version>` | 팔코의 `{{< latest >}}`와 같은 특정 버전 |
|[latest](https://hub.docker.com/r/falcosecurity/falco-driver-loader/tags)| `docker pull falcosecurity/falco-driver-loader:latest` | 빌드 툴체인을 갖춘 `falco-driver-loader`의 최신 버전 |
|[*version*](https://hub.docker.com/r/falcosecurity/falco-driver-loader/tags)| `docker pull falcosecurity/falco-driver-loader:<version>` | 빌드 툴체인을 갖춘 `falco-driver-loader`의 `{{< latest >}}`와 같은 특정 버전 |
|[latest](https://hub.docker.com/r/falcosecurity/falco/tags)| `docker pull falcosecurity/falco:latest` | `falco-driver-loader`가 포함된 최신 버전 |
|[*version*](https://hub.docker.com/r/falcosecurity/falco/tags)| `docker pull falcosecurity/falco:<version>` | `falco-driver-loader`가 포함된 `{{< latest >}}`와 같은 특정 버전 |

사용 가능한 전체 이미지 목록은 [여기](https://github.com/falcosecurity/falco/tree/master/docker)에서 확인할 수 있다.

[1]: https://download.falco.org/?prefix=packages/rpm-dev/
[2]: https://download.falco.org/?prefix=packages/rpm/
[3]: https://download.falco.org/?prefix=packages/deb-dev/stable/
[4]: https://download.falco.org/?prefix=packages/deb/stable/
[5]: https://download.falco.org/?prefix=packages/bin-dev/x86_64/
[6]: https://download.falco.org/?prefix=packages/bin/x86_64/
