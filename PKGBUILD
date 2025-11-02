# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2024, 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$( \
  uname \
    -o)"
_evmfs_available="$( \
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
if [[ "${_os}" == "Android" ]]; then
  _node="nodejs-lts"
fi
if [[ ! -v "_npm" ]]; then
  if [[ "${_evmfs}" == "true" ]]; then
    _npm="false"
  elif [[ "${_evmfs}" == "true" ]]; then
    _npm="true"
  fi
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="github"
fi
if [[ ! -v "_git" ]]; then
  if [[ "${_evmfs}" == "true" ]]; then
    _git="true"
  elif [[ "${_evmfs}" == "false" ]]; then
    _git="false"
  fi
fi
_archive_format="tgz"
if [[ ! -v "${_archive_format}" ]]; then
  if [[ "${_npm}" == "false" ]]; then
    if [[ "${_evmfs}" == "true" ]]; then
      _archive_format="bundle"
    elif [[ "${_evmfs}" == "false" ]]; then
      if [[ "${_git_http}" == "github" ]]; then
        _archive_format="zip"
      fi
    fi
  fi
fi
_pkg=std-path
pkgbase="${_node}-${_pkg}"
pkgname=(
  "${pkgbase}"
)
_pkgdesc=(
  "JavaScript utilities"
  "for working with"
  "OS-specific file paths."
)
pkgdesc="${_pkgdesc[*]}"
pkgver=1.1.2
_commit="2811b95532c1dc51e8c7463ed86f99daed1a5381"
pkgrel=1
arch=(
  'any'
)
_http="https://${_git_http}.com"
_ns="Swatinem"
url="${_http}/${_ns}/${_pkg}"
license=(
  'LGPL3'
)
depends=(
  "${_node}"
)
provides=(
  "${_pkg}=${pkgver}"
)
makedepends=(
  "npm"
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
if [[ "${_npm}" == "true" ]]; then
  _tag="${pkgver}"
elif [[ "${_npm}" == "false" ]]; then
  _tag="${_commit}"
fi
_tarname="${_pkg}-${_tag}"
_tarfile="${_tarname}.${_archive_format}"
_sum="d49906ca8f1488dc73fb20e692523cbd1f778caaecefeb368166e0fb6d9d78ef"
_sig_sum="6122a66cdcdbfe0c58c0744db63d3ce9cebcf2c12080a5765f149b964807d8a0"
_bundle_sum="4cce8e175ca17028860c739112cbb9be3052efc44e12026b0a83632ad46927b0"
_bundle_sig_sum="737d7de2729723936ce4375b4092733131a98f5715898d701227dda6378d8dac"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
# Truocolo
_evmfs_ns="0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_bundle_uri="${_evmfs_dir}/${_bundle_sum}"
_bundle_src="${_tarfile}::${_bundle_uri}"
_evmfs_uri="${_evmfs_dir}/${_sum}"
_evmfs_src="${_tarfile}::${_evmfs_uri}"
_sig_uri="${_evmfs_dir}/${_sig_sum}"
_sig_src="${_tarfile}.sig::${_sig_uri}"
_bundle_sig_uri="${_evmfs_dir}/${_bundle_sig_sum}"
_bundle_sig_src="${_tarfile}.sig::${_bundle_sig_uri}"
_npm_http="http://registry.npmjs.org"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  makedepends+=(
    "evmfs"
  )
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_evmfs_src}"
  elif [[ "${_npm}" == "false" ]]; then
    _uri="${_bundle_uri}"
    _sum="${_bundle_sum}"
    _sig_src="${_bundle_sig_src}"
    _sig_sum="${_bundle_sig_sum}"
  fi
  source+=(
    "${_sig_src}"
  )
  sha256sums+=(
    "${_sig_sum}"
  )
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_npm_http}/${_pkg}/-/${_tarfile}"
  fi
fi
_src="${_tarfile}::${_uri}"
source+=(
  "${_src}"
)
sha256sums+=(
  "${_sum}"
)
noextract=(
  "${_tarfile}"
)
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
          "master"
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
    cd \
      "${_tarname}"
    npm \
      install
    tsc
      "${_tsc_opts[@]}"
    rollup \
      "${_rollup_opts[@]}"
    mkdir \
      -p \
      "build"
    cp \
      -r \
      "${_files[@]}" \
      "build"
    cd \
      "build"
    npm \
      pack
    mv \
      "${_pkg}-${pkgver}.tgz" \
      "${srcdir}/${_pkg}-${pkgver}.tgz"
  fi
}

package_nodejs-rollup-plugin-dts() {
  local \
    _npm_options=() \
    _find_opts=()
  _npm_options=(
    -g 
    # --user 
    #   root 
    --prefix 
      "${pkgdir}/usr"
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
    "${srcdir}/${_pkg}-${pkgver}.tgz"
  rm \
    -fr \
      "${pkgdir}/usr/etc"
  # Fix npm derp
  find \
    "${pkgdir}/usr" \
    "${_find_opts[@]}"
}

# vim:set sw=2 sts=-1 et:
