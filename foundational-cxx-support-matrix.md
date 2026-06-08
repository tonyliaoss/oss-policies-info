# Foundational C++ Support

The relevant policies are described at https://opensource.google/documentation/policies/cplusplus-support.
This document captures the specific version numbers as resolved by those policies.

Note that some of these version supports apply broadly to other languages as well, and are not exclusive to C++.

## Linux distributions

### Cited Text

> We will support releases of the following Linux distributions until the vendor
> drops support.

Vendor support is obtained from published support windows.
https://endoflife.date/ consolidates these support windows on top of providing a
visualization.

### Implied Support Matrix

| Distribution    | Supported Version      | Last Changed | Next Change [^next-change] |
|-----------------|------------------------|--------------|-------------|
| Alpine          | >= 3.21                | 2026-04-01   | 2026-11-01 |
| Debian          | >= 13                  | 2026-06-08   | 2027-06-30 |
| Fedora          | >= 43                  | 2026-06-08   | 2026-12-10 |
| openSUSE        | >= Leap 16.0           | 2026-05-01   | 2027-10-31 |
| Ubuntu LTS      | >= 22.04               | 2025-06-04   | 2027-05-01 |
| RHEL            | >= 9                   | 2024-07-01   | 2027-06-01 |
| RockyLinux      | >= 9                   | 2024-07-01   | 2027-06-01 |

## Windows

### Cited Text

> We will build using the **newest Windows** server platform available.
>
> We will support all the Windows versions that Microsoft supports.
> i.  [Windows client support](https://docs.microsoft.com/en-us/windows/release-health/supported-versions-windows-client)
> ii. [Windows server support](https://endoflife.date/windows-server)

### Implied Support Matrix

| Dimension       | Supported Version      | Last Changed | Next Change [^next-change] |
|-----------------|------------------------|--------------|-------------|
| Windows Server  | >= 2022                | 2024-01-22   | 2026-10-13 |
| Windows Client  | >= 11                  | 2025-12-16   | 2026-10-13 |

## macOS

### Cited Text

> We will build using the newest XCode available.
> We will support back to the oldest macOS target platform needed by Chrome.
> We will support back to the oldest iOS target platform that has a simulator.

Note that Chrome has announced a update in minimum required OS version in
[151](https://support.google.com/chrome/thread/404150391/sunsetting-support-for-macos-12-monterey-in-mid-2026?hl=en).
In addition, the
[Chrome browser system requirements](https://support.google.com/chrome/a/answer/7100626)
page shows Chrome's support timelines.

### Implied Support Matrix
| Dimension         | Supported Version      | Last Changed | Next Change [^next-change] |
|-------------------|------------------------|--------------|-------------|
| Xcode             | >= 26                  | 2025-09-15   | 2026-09-15 |
| macOS (target)    | >= 13 (Ventura)        | 2026-06-06   | 2027-01-01 |
| iOS  (target)     | >= 15                  | 2025-12-16   | 2026-09-15 |

## Android NDK

### Cited Text

> We will support Android -- we will build using the newest Android NDK and
> target its lowest supported API level (example
> [meta/platforms.json](https://android.googlesource.com/platform/ndk.git/+/refs/heads/master/meta/platforms.json)).

### Implied Support Matrix
| Dimension              | Supported Version      | Last Changed | Next Change [^next-change] |
|------------------------|------------------------|--------------|----------------------------|
| Android API (target)   | >= 21                  | 2022-09-18   |                            |

## Compilers, tools, build systems

### Cited Text

> 1. We do not support any compiler that is EOL as defined by the vendor.
> 1. We support GCC and Clang on our supported Linux distros (see above). We
>    support the version installed by default (e.g., apt install gcc), unless
>    we've explicitly excluded support for that version because it doesn't
>    support other required policies of ours (e.g., we agree to remove GCC 4.8
>    because of its incomplete C++11 support, as well as clang 3.x). If we
>    cannot support the default version, we may instead support a newer version
>    that's available from the vendor (e.g., devtoolset-7 on RHEL/CentOS 7)
> 1. We support Apple Clang on our supported XCode version.
> 1. We support MSVC on our supported Windows versions.
>    1. We support the MSVC versions that are in the Mainstream Support window
>       as defined by Microsoft's Fixed Lifecycle Policy.


### Implied Support Matrix

| Dimension       | Supported Version      | Last Changed | Next Change [^next-change] |
|-----------------|------------------------|--------------|-------------|
| C++ Version     | >= 17                  | 2024-12-17   | 2027-12-15  |
| CMake           | >= 3.22                | 2025-06-04   | 2027-05-01 [^cmake] |
| Bazel           | 8 LTS                  | 2025-12-16   | 2026-12-01  |
| GCC             | >= 10                  | 2026-05-01   | 2026-06-30 [^gcc] |
| Clang           | >= 14.0.0              | 2025-06-04   | 2027-05-01 [^clang] |
| MSVC            | >= 2022                | 2024-04-29   | 2027-01-12  |
| Apple Clang     | >= 17                  | 2025-12-19   | 2026-07-01 |
| glibc           | >= 2.27                | 2024-07-09   | TBD [^glibc] |
| musl            | >= 1.2.5               | 2026-04-01   | 2026-11-01 |

[^next-change]: This is an estimated date. The actual date may change if the
vendor (or community, as applicable) extends or shortens the lifetime of the
dimension in question.

[^cmake]: We support the oldest version of CMake that ships with one of the
supported distros. Currently that is CMake 3.22 as Ubuntu 22.04 ships with this
version.

[^gcc]: We support the oldest version of GCC that ships with one of the
supported distros. Currently that is GCC 10 as Debian 11 ships with this
version.

[^clang]: We support the oldest version of Clang that ships with one of the
supported distros. Currently that is Clang 14.0 as Ubuntu 22.04 ships with
this version.

[^glibc]: We plan to support glibc >= 2.27 until further notice.

### Notes


[devtoolset-7]: https://www.softwarecollections.org/en/scls/rhscl/devtoolset-7/
