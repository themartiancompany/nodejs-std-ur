# SPDX-License-Identifier: AGPL-3.0

#    -----------------------------------------------------
#    Copyright © 2024, 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    -----------------------------------------------------
#
#    This program is free software: you can redistribute
#    it and/or modify it under the terms of the
#    GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of
#    the License, or (at your option) any later version.
#
#    This program is distributed in the hope that it
#    will be useful, but WITHOUT ANY WARRANTY;
#    without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
#    See the GNU Affero General Public License for
#    more details.
#
#    You should have received a copy of the
#    GNU Affero General Public License
#    along with this program.
#    If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$(
  uname \
    -o)"
_evmfs_available="$(
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
_node="nodejs"
if [[ ! -v "_lts" ]]; then
  if [[ "${_os}" == "Android" ]]; then
    _lts="true"
  fi
  _lts="false"
fi
if [[ ! -v "_npm" ]]; then
  if [[ "${_evmfs}" == "true" ]]; then
    _npm="false"
  elif [[ "${_evmfs}" == "false" ]]; then
    _npm="false"
  fi
fi
if [[ ! -v "_git_service" ]]; then
  _git_service="github"
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="${_git_service}"
fi
if [[ ! -v "_git" ]]; then
  if [[ "${_evmfs}" == "true" ]]; then
    _git="false"
  elif [[ "${_evmfs}" == "false" ]]; then
    _git="false"
  fi
fi
if [[ ! -v "_archive_format" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _archive_format="tgz"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_evmfs}" == "true" ]]; then
      if [[ "${_git}" == "true" ]]; then
        _archive_format="bundle"
      elif [[ "${_git}" == "false" ]]; then
        _archive_format="tar.gz"
      fi
    elif [[ "${_evmfs}" == "false" ]]; then
      _archive_format="tar.gz"
      if [[ "${_git_http}" == "github" ]]; then
        _archive_format="zip"
      fi
    fi
  fi
fi
_proj=deno
_pkg=std
pkgbase="${_node}-${_pkg}"
pkgname=(
  "${pkgbase}-internal"
  "${pkgbase}-path"
)
_pkgdesc=(
  "JavaScript utilities"
  "for working with"
  "OS-specific file paths."
)
pkgdesc="${_pkgdesc[*]}"
pkgver=2025.10.07a
_internal_pkgver="1.0.17"
_path_pkgver="1.1.5"
_bundle_commit="a0acfb0084c252ec854fa04a2caf7c043f201375"
_internal_commit="6a52f4f84d9e7e6614744565aac986af6a339af2"
_path_commit="7cf8de027f5deac33fc3b5bfeed3f3a2e427076f"
_commit="43de5dfd4f389f5835cd2ae91389903396228e1b"
pkgrel=5
arch=(
  'any'
)
_http="https://${_git_http}.com"
if [[ ! -v "_ns" ]]; then
  _ns="${_proj}land"
  _ns="themartiancompany"
fi
url="${_http}/${_ns}/${_pkg}"
_url="${url}"
license=(
  'MIT'
)
_node_pkg="${_node}"
if [[ "${_lts}" == "true" ]]; then
  _node_pkg="${_node}-lts"
fi
depends=(
  "${_node_pkg}"
)
provides=(
  "${_pkg}=${pkgver}"
  "${_proj}-${_pkg}=${pkgver}"
)
makedepends=(
  "deno"
  # "npm"
)
if [[ "${_npm}" == "false" ]]; then
  makedepends+=(
    "${_node}-rollup"
    "typescript"
  )
fi
if [[ "${_git}" == "true" ]]; then
  makedepends+=(
    "git"
  )
fi
if [[ ! -v "_tag_name" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _tag_name="tag"
  elif [[ "${_npm}" == "false" ]]; then
    _tag_name="commit"
  fi
fi
if [[ ! -v "_tag" ]]; then
  if [[ "${_tag_name}" == "commit" ]]; then
    _tag="${_commit}"
  elif [[ "${_tag_name}" == "tag" ]]; then
    _tag="${pkgver}"
  fi
fi
_tarname="${_pkg}-${_tag}"
_internalname="${_proj}-${_pkg}-internal-bin-${_internal_commit}"
_pathname="${_proj}-${_pkg}-path-bin-${_path_commit}"
_pathfile="${_pathname}.${_archive_format}"
_internalfile="${_internalname}.${_archive_format}"
_tarfile="${_tarname}.${_archive_format}"
_sum="d49906ca8f1488dc73fb20e692523cbd1f778caaecefeb368166e0fb6d9d78ef"
_github_sum="3259c5391af592923f2f88b597a2eac606fcf030e12d2514b992c6699ca1b2fe"
_github_sig_sum="8922526c845a655c20599019f7dd1c401496fb075d3655e934758455c958c7c7"
_sig_sum="6122a66cdcdbfe0c58c0744db63d3ce9cebcf2c12080a5765f149b964807d8a0"
_internal_sum="cc08c83d9ebc2ac6f6f542e11e1ffff4acff8f353c2f2e8089ee8bc3a6dd5385"
_internal_sig_sum="a4c07da9303f7f59aad15564007bc93bc68b570fe7318b62aa1861563beeefb6"
_path_sum="4f25d2b24fcd0ab7d7428eb0fe412c4be4225e2366f7ec0594d26cdd5818b102"
_path_sig_sum="c3d3bf4eba130e9c25de712a21cb86c493e3da51382b163147ba3272b08c4921"
_bundle_sum="f8b6b32c486e99e7b58953ca42a50038e5472a903f3eb0af77fa66ee3658d2e6"
_bundle_sig_sum="77d3a4697e52b066941ad1dea11022aaeb01ebbf0ea4ebb925bb611face8ba2f"
# Truocolo
_evmfs_ns="0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_bundle_uri="${_evmfs_dir}/${_bundle_sum}"
_bundle_src="${_tarfile}::${_bundle_uri}"
_internal_uri="${_evmfs_dir}/${_internal_sum}"
_internal_src="${_internalfile}::${_internal_uri}"
_path_uri="${_evmfs_dir}/${_path_sum}"
_path_src="${_pathfile}::${_path_uri}"
_evmfs_uri="${_evmfs_dir}/${_sum}"
_evmfs_src="${_tarfile}::${_evmfs_uri}"
_sig_uri="${_evmfs_dir}/${_sig_sum}"
_sig_src="${_tarfile}.sig::${_sig_uri}"
_bundle_sig_uri="${_evmfs_dir}/${_bundle_sig_sum}"
_bundle_sig_src="${_tarfile}.sig::${_bundle_sig_uri}"
_internal_sig_uri="${_evmfs_dir}/${_internal_sig_sum}"
_internal_sig_src="${_internalfile}.sig::${_internal_sig_uri}"
_path_sig_uri="${_evmfs_dir}/${_path_sig_sum}"
_path_sig_src="${_pathfile}.sig::${_path_sig_uri}"
_npm_http="http://registry.npmjs.org"
_npm_http="http://npm.sr.io"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  makedepends+=(
    "evmfs"
  )
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_evmfs_src}"
    _src="${_tarfile}::${_uri}"
    source+=(
      "${_src}"
      "${_sig_src}"
    )
    sha256sums+=(
      "${_sum}"
      "${_sig_sum}"
    )
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == "true" ]]; then
      _uri="${_bundle_uri}"
      _sum="${_bundle_sum}"
      _sig_src="${_bundle_sig_src}"
      _sig_sum="${_bundle_sig_sum}"
      source+=(
        "${_src}"
        "${_sig_src}"
      )
      sha256sums+=(
        "${_sum}"
        "${_sig_sum}"
      )
    elif [[ "${_git}" == "false" ]]; then
      source+=(
        "${_internal_src}"
        "${_internal_sig_src}"
        "${_path_src}"
        "${_path_sig_src}"
      )
      sha256sums+=(
        "${_internal_sum}"
        "${_internal_sig_sum}"
        "${_path_sum}"
        "${_path_sig_sum}"
      )
    fi
  fi
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_npm_http}/${_pkg}/-/${_tarfile}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == true ]]; then
      _uri="git+${_url}#${_tag_name}=${_tag}?signed"
      _tarfile="${_tarname}"
      _sum="SKIP"
    elif [[ "${_git}" == false ]]; then
      _uri=""
      if [[ "${_git_service}" == "github" ]]; then
        if [[ "${_tag_name}" == "commit" ]]; then
          _uri="${_url}/archive/${_commit}.${_archive_format}"
          _sum="${_github_sum}"
        fi
      elif [[ "${_git_service}" == "gitlab" ]]; then
        if [[ "${_tag_name}" == "commit" ]]; then
          _uri="${_url}/-/archive/${_tag}/${_tag}.${_archive_format}"
        fi
      fi
      _src="${_tarfile}::${_uri}"
    fi
  fi
  _src="${_tarfile}::${_uri}"
  source+=(
    "${_src}"
  )
  sha256sums+=(
    "${_sum}"
  )
fi
if [[ "${_npm}" == "true" ]]; then
  noextract=(
    "${_tarfile}"
  )
fi
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  'DD6732B02E6C88E9E27E2E0D5FC6652B9D9A6C01'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

prepare() {
  if [[ "${_evmfs}" == "true" && \
        "${_git}" == "true" ]]; then
    git \
      init \
      "${srcdir}/${_tarname}"
    cd \
      "${_tarname}"
    git \
      "${_git_opts[@]}" \
      remote \
        add \
          origin \
          "${srcdir}/${_tarfile}" || \
      true
    git \
      "${_git_opts[@]}" \
      pull \
        origin \
          "main"
  fi
}

build() {
  local \
    _rollup_opts=() \
    _files=()
  _files+=(
    "COPYING"
    "COPYING.LESSER"
    "README.md"
    "dist"
    "package.json"
  )
  _rollup_opts+=(
    --config
      ".build/rollup.config.js"
  )
  if [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == "true" ]]; then
       cd \
         "${_tarname}"
       # See https://github.com/denoland/std/issues/6864
    elif [[ "${_git}" == "false" ]]; then
      cd \
        "${srcdir}/${_internalname}"
      npm \
        pack
      mv \
        *".tgz" \
        "${srcdir}"
      cd \
        "${srcdir}/${_pathname}"
      npm \
        pack
      mv \
        *".tgz" \
        "${srcdir}"
    fi
  fi
}

_npm_package() {
  local \
    _pkg="${1}" \
    _pkgdir="${2}" \
    _npm_options=() \
    _find_opts=()
  _npm_options=(
    -g 
    # --user 
    #   root 
    --prefix 
      "${_pkgdir}/usr"
  )
  find_opts+=(
    -type
      "d"
    -exec
      chmod
        755
        '{}'
        +
  )
  npm \
    install \
    "${_npm_options[@]}" \
    "${_pkg}"
  rm \
    -fr \
      "${_pkgdir}/usr/etc"
  # Fix npm derp
  find \
    "${_pkgdir}/usr" \
    "${_find_opts[@]}"
}

package_nodejs-std() {
  _npm_package \
    "${srcdir}/${_pkg}-${pkgver}.tgz" \
    "${pkgdir}"
}

package_nodejs-std-internal() {
  local \
    _pkgdesc=()
  _ns="themartiancompany"
  url="${_http}/${_ns}/${_proj}-${_pkg}-internal-bin"
  _archive="${_ns}-${_pkg}__internal-${_internal_pkgver}.tgz"
  _pkgdesc=(
    "The internal package for Deno"
    "Standard Library."
  )
  pkgdesc="${_pkgdesc[*]}"
  provides=(
    "${pkgbase}=${pkgver}"
    "${_proj}-${_pkg}=${pkgver}"
    "${_node}-${_proj}-${_pkg}=${pkgver}"
  )
  _npm_package \
    "${srcdir}/${_archive}" \
    "${pkgdir}"
}

package_nodejs-std-path() {
  local \
    _pkgdesc=()
  _ns="themartiancompany"
  url="${_http}/${_ns}/${_proj}-${_pkg}-path-bin"
  _archive="${_ns}-${_pkg}__path-${_path_pkgver}.tgz"
  _pkgdesc=(
    "Utilities for working with"
    "file system paths."
  )
  pkgdesc="${_pkgdesc[*]}"
  depends+=(
    "${_node}-${_pkg}-internal"
  )
  provides=(
    "${pkgbase}=${pkgver}"
    "${_proj}-${_pkg}=${pkgver}"
    "${_node}-${_proj}-${_pkg}=${pkgver}"
  )
  _npm_package \
    "${srcdir}/${_archive}" \
    "${pkgdir}"
}

# vim:set sw=2 sts=-1 et:
