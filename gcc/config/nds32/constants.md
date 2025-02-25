;; Constant defintions of Andes NDS32 cpu for GNU compiler
;; Copyright (C) 2012-2018 Free Software Foundation, Inc.
;; Contributed by Andes Technology Corporation.
;;
;; This file is part of GCC.
;;
;; GCC is free software; you can redistribute it and/or modify it
;; under the terms of the GNU General Public License as published
;; by the Free Software Foundation; either version 3, or (at your
;; option) any later version.
;;
;; GCC is distributed in the hope that it will be useful, but WITHOUT
;; ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
;; or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public
;; License for more details.
;;
;; You should have received a copy of the GNU General Public License
;; along with GCC; see the file COPYING3.  If not see
;; <http://www.gnu.org/licenses/>.


;; Register numbers.
(define_constants
  [(R8_REGNUM  8)
   (TA_REGNUM 15)
   (TP_REGNUM 25)
   (FP_REGNUM 28)
   (GP_REGNUM 29)
   (LP_REGNUM 30)
   (SP_REGNUM 31)
  ])


;; The unpec operation index.
(define_c_enum "unspec_element" [
  UNSPEC_COPYSIGN
  UNSPEC_FCPYNSD
  UNSPEC_FCPYNSS
  UNSPEC_FCPYSD
  UNSPEC_FCPYSS
  UNSPEC_CLIP
  UNSPEC_CLIPS
  UNSPEC_CLO
  UNSPEC_PBSAD
  UNSPEC_PBSADA
  UNSPEC_BSE
  UNSPEC_BSE_2
  UNSPEC_BSP
  UNSPEC_BSP_2
  UNSPEC_FFB
  UNSPEC_FFMISM
  UNSPEC_FLMISM
  UNSPEC_KDMBB
  UNSPEC_KDMBT
  UNSPEC_KDMTB
  UNSPEC_KDMTT
  UNSPEC_KHMBB
  UNSPEC_KHMBT
  UNSPEC_KHMTB
  UNSPEC_KHMTT
  UNSPEC_KSLRAW
  UNSPEC_KSLRAWU
  UNSPEC_SVA
  UNSPEC_SVS
  UNSPEC_WSBH
  UNSPEC_LWUP
  UNSPEC_LBUP
  UNSPEC_SWUP
  UNSPEC_SBUP
  UNSPEC_UALOAD_HW
  UNSPEC_UALOAD_W
  UNSPEC_UALOAD_DW
  UNSPEC_UASTORE_HW
  UNSPEC_UASTORE_W
  UNSPEC_UASTORE_DW
  UNSPEC_GOTINIT
  UNSPEC_GOT
  UNSPEC_GOTOFF
  UNSPEC_PLT
  UNSPEC_TLSGD
  UNSPEC_TLSLD
  UNSPEC_TLSIE
  UNSPEC_TLSLE
  UNSPEC_ROUND
  UNSPEC_VEC_COMPARE
  UNSPEC_KHM
  UNSPEC_KHMX
  UNSPEC_CLIP_OV
  UNSPEC_CLIPS_OV
  UNSPEC_BITREV
  UNSPEC_KABS
  UNSPEC_LOOP_END
  UNSPEC_TLS_DESC
  UNSPEC_TLS_IE
  UNSPEC_ADD32
  UNSPEC_ICT
  UNSPEC_KADDH
  UNSPEC_KSUBH
])

;; The unspec_volatile operation index.
(define_c_enum "unspec_volatile_element" [
  UNSPEC_VOLATILE_EH_RETURN
  UNSPEC_VOLATILE_ISYNC
  UNSPEC_VOLATILE_ISB
  UNSPEC_VOLATILE_DSB
  UNSPEC_VOLATILE_MSYNC
  UNSPEC_VOLATILE_MSYNC_ALL
  UNSPEC_VOLATILE_MSYNC_STORE
  UNSPEC_VOLATILE_MFSR
  UNSPEC_VOLATILE_MFUSR
  UNSPEC_VOLATILE_MTSR
  UNSPEC_VOLATILE_MTUSR
  UNSPEC_VOLATILE_SETGIE_EN
  UNSPEC_VOLATILE_SETGIE_DIS
  UNSPEC_VOLATILE_FMFCSR
  UNSPEC_VOLATILE_FMTCSR
  UNSPEC_VOLATILE_FMFCFG
  UNSPEC_VOLATILE_JR_ITOFF
  UNSPEC_VOLATILE_JR_TOFF
  UNSPEC_VOLATILE_JRAL_ITON
  UNSPEC_VOLATILE_JRAL_TON
  UNSPEC_VOLATILE_RET_ITOFF
  UNSPEC_VOLATILE_RET_TOFF
  UNSPEC_VOLATILE_STANDBY_NO_WAKE_GRANT
  UNSPEC_VOLATILE_STANDBY_WAKE_GRANT
  UNSPEC_VOLATILE_STANDBY_WAKE_DONE
  UNSPEC_VOLATILE_TEQZ
  UNSPEC_VOLATILE_TNEZ
  UNSPEC_VOLATILE_TRAP
  UNSPEC_VOLATILE_SETEND_BIG
  UNSPEC_VOLATILE_SETEND_LITTLE
  UNSPEC_VOLATILE_BREAK
  UNSPEC_VOLATILE_SYSCALL
  UNSPEC_VOLATILE_NOP
  UNSPEC_VOLATILE_LLW
  UNSPEC_VOLATILE_SCW
  UNSPEC_VOLATILE_CCTL_L1D_INVALALL
  UNSPEC_VOLATILE_CCTL_L1D_WBALL_ALVL
  UNSPEC_VOLATILE_CCTL_L1D_WBALL_ONE_LVL
  UNSPEC_VOLATILE_CCTL_IDX_WRITE
  UNSPEC_VOLATILE_CCTL_IDX_READ
  UNSPEC_VOLATILE_CCTL_VA_WBINVAL_L1
  UNSPEC_VOLATILE_CCTL_VA_WBINVAL_LA
  UNSPEC_VOLATILE_CCTL_IDX_WBINVAL
  UNSPEC_VOLATILE_CCTL_VA_LCK
  UNSPEC_VOLATILE_DPREF_QW
  UNSPEC_VOLATILE_DPREF_HW
  UNSPEC_VOLATILE_DPREF_W
  UNSPEC_VOLATILE_DPREF_DW
  UNSPEC_VOLATILE_TLBOP_TRD
  UNSPEC_VOLATILE_TLBOP_TWR
  UNSPEC_VOLATILE_TLBOP_RWR
  UNSPEC_VOLATILE_TLBOP_RWLK
  UNSPEC_VOLATILE_TLBOP_UNLK
  UNSPEC_VOLATILE_TLBOP_PB
  UNSPEC_VOLATILE_TLBOP_INV
  UNSPEC_VOLATILE_TLBOP_FLUA
  UNSPEC_VOLATILE_ENABLE_INT
  UNSPEC_VOLATILE_DISABLE_INT
  UNSPEC_VOLATILE_SET_PENDING_SWINT
  UNSPEC_VOLATILE_CLR_PENDING_SWINT
  UNSPEC_VOLATILE_CLR_PENDING_HWINT
  UNSPEC_VOLATILE_GET_ALL_PENDING_INT
  UNSPEC_VOLATILE_GET_PENDING_INT
  UNSPEC_VOLATILE_SET_INT_PRIORITY
  UNSPEC_VOLATILE_GET_INT_PRIORITY
  UNSPEC_VOLATILE_SET_TRIG_LEVEL
  UNSPEC_VOLATILE_SET_TRIG_EDGE
  UNSPEC_VOLATILE_GET_TRIG_TYPE
  UNSPEC_VOLATILE_RELAX_GROUP
  UNSPEC_VOLATILE_POP25_RETURN
  UNSPEC_VOLATILE_UNALIGNED_FEATURE
  UNSPEC_VOLATILE_ENABLE_UNALIGNED
  UNSPEC_VOLATILE_DISABLE_UNALIGNED
  UNSPEC_VOLATILE_RDOV
  UNSPEC_VOLATILE_CLROV
])

;; ------------------------------------------------------------------------
