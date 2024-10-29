
if (CONFIG_MCUX_COMPONENT_middleware.openh264.api)
    mcux_add_source(
        SOURCES codec/api/svc/codec_api.h
                codec/api/svc/codec_app_def.h
                codec/api/svc/codec_def.h
                codec/api/svc/codec_ver.h
    )
    mcux_add_include(
        INCLUDES codec/api/svc
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.common)
    mcux_add_source(
        SOURCES codec/common/inc/asmdefs_mmi.h
                codec/common/inc/copy_mb.h
                codec/common/inc/cpu.h
                codec/common/inc/cpu_core.h
                codec/common/inc/crt_util_safe_x.h
                codec/common/inc/deblocking_common.h
                codec/common/inc/expand_pic.h
                codec/common/inc/golomb_common.h
                codec/common/inc/intra_pred_common.h
                codec/common/inc/ls_defines.h
                codec/common/inc/macros.h
                codec/common/inc/mc.h
                codec/common/inc/measure_time.h
                codec/common/inc/memory_align.h
                codec/common/inc/sad_common.h
                codec/common/inc/typedefs.h
                codec/common/inc/utils.h
                codec/common/inc/version.h
                codec/common/inc/wels_common_defs.h
                codec/common/inc/wels_const_common.h
                codec/common/inc/welsCodecTrace.h
                codec/common/inc/WelsList.h
                codec/common/inc/WelsLock.h
                codec/common/inc/WelsTask.h
                codec/common/inc/WelsTaskThread.h
                codec/common/inc/WelsThread.h
                codec/common/inc/WelsThreadLib.h
                codec/common/inc/WelsThreadPool.h
                codec/common/src/common_tables.cpp
                codec/common/src/copy_mb.cpp
                codec/common/src/cpu.cpp
                codec/common/src/crt_util_safe_x.cpp
                codec/common/src/deblocking_common.cpp
                codec/common/src/expand_pic.cpp
                codec/common/src/intra_pred_common.cpp
                codec/common/src/mc.cpp
                codec/common/src/memory_align.cpp
                codec/common/src/sad_common.cpp
                codec/common/src/utils.cpp
                codec/common/src/welsCodecTrace.cpp
                codec/common/src/WelsTaskThread.cpp
                codec/common/src/WelsThread.cpp
                codec/common/src/WelsThreadLib.cpp
                codec/common/src/WelsThreadPool.cpp
    )
    mcux_add_include(
        INCLUDES codec/common/inc
    )

    mcux_add_configuration(
        CC "-D__NXP_MSDK__"
        CX "-D__NXP_MSDK__"
    )

    mcux_add_iar_configuration(
        CX "--diag_suppress Pe815,Pe111,Pe186,Pe068,Pe177"
    )

    mcux_add_armgcc_configuration(
        CX "-Wno-format\
            -Wno-strict-aliasing"
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.decoder)
    mcux_add_source(
        SOURCES codec/decoder/core/inc/au_parser.h
                codec/decoder/core/inc/bit_stream.h
                codec/decoder/core/inc/cabac_decoder.h
                codec/decoder/core/inc/deblocking.h
                codec/decoder/core/inc/dec_frame.h
                codec/decoder/core/inc/dec_golomb.h
                codec/decoder/core/inc/decode_mb_aux.h
                codec/decoder/core/inc/decode_slice.h
                codec/decoder/core/inc/decoder.h
                codec/decoder/core/inc/decoder_context.h
                codec/decoder/core/inc/decoder_core.h
                codec/decoder/core/inc/error_code.h
                codec/decoder/core/inc/error_concealment.h
                codec/decoder/core/inc/fmo.h
                codec/decoder/core/inc/get_intra_predictor.h
                codec/decoder/core/inc/manage_dec_ref.h
                codec/decoder/core/inc/mb_cache.h
                codec/decoder/core/inc/memmgr_nal_unit.h
                codec/decoder/core/inc/mv_pred.h
                codec/decoder/core/inc/nal_prefix.h
                codec/decoder/core/inc/nalu.h
                codec/decoder/core/inc/parameter_sets.h
                codec/decoder/core/inc/parse_mb_syn_cabac.h
                codec/decoder/core/inc/parse_mb_syn_cavlc.h
                codec/decoder/core/inc/pic_queue.h
                codec/decoder/core/inc/picture.h
                codec/decoder/core/inc/rec_mb.h
                codec/decoder/core/inc/slice.h
                codec/decoder/core/inc/vlc_decoder.h
                codec/decoder/core/inc/wels_common_basis.h
                codec/decoder/core/inc/wels_const.h
                codec/decoder/core/inc/wels_decoder_thread.h
                codec/decoder/core/src/au_parser.cpp
                codec/decoder/core/src/bit_stream.cpp
                codec/decoder/core/src/cabac_decoder.cpp
                codec/decoder/core/src/deblocking.cpp
                codec/decoder/core/src/decode_mb_aux.cpp
                codec/decoder/core/src/decode_slice.cpp
                codec/decoder/core/src/decoder.cpp
                codec/decoder/core/src/decoder_core.cpp
                codec/decoder/core/src/decoder_data_tables.cpp
                codec/decoder/core/src/error_concealment.cpp
                codec/decoder/core/src/fmo.cpp
                codec/decoder/core/src/get_intra_predictor.cpp
                codec/decoder/core/src/manage_dec_ref.cpp
                codec/decoder/core/src/memmgr_nal_unit.cpp
                codec/decoder/core/src/mv_pred.cpp
                codec/decoder/core/src/parse_mb_syn_cabac.cpp
                codec/decoder/core/src/parse_mb_syn_cavlc.cpp
                codec/decoder/core/src/pic_queue.cpp
                codec/decoder/core/src/rec_mb.cpp
                codec/decoder/core/src/wels_decoder_thread.cpp
                codec/decoder/plus/inc/welsDecoderExt.h
                codec/decoder/plus/src/welsDecoderExt.cpp
    )
    mcux_add_include(
        INCLUDES codec/decoder/core/inc
                 codec/decoder/plus/inc
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.encoder)
    mcux_add_source(
        SOURCES codec/encoder/core/inc/as264_common.h
                codec/encoder/core/inc/au_set.h
                codec/encoder/core/inc/deblocking.h
                codec/encoder/core/inc/decode_mb_aux.h
                codec/encoder/core/inc/dq_map.h
                codec/encoder/core/inc/encode_mb_aux.h
                codec/encoder/core/inc/encoder.h
                codec/encoder/core/inc/encoder_context.h
                codec/encoder/core/inc/extern.h
                codec/encoder/core/inc/get_intra_predictor.h
                codec/encoder/core/inc/mb_cache.h
                codec/encoder/core/inc/md.h
                codec/encoder/core/inc/mt_defs.h
                codec/encoder/core/inc/mv_pred.h
                codec/encoder/core/inc/nal_encap.h
                codec/encoder/core/inc/param_svc.h
                codec/encoder/core/inc/parameter_sets.h
                codec/encoder/core/inc/paraset_strategy.h
                codec/encoder/core/inc/picture.h
                codec/encoder/core/inc/picture_handle.h
                codec/encoder/core/inc/rc.h
                codec/encoder/core/inc/ref_list_mgr_svc.h
                codec/encoder/core/inc/sample.h
                codec/encoder/core/inc/set_mb_syn_cabac.h
                codec/encoder/core/inc/set_mb_syn_cavlc.h
                codec/encoder/core/inc/slice.h
                codec/encoder/core/inc/slice_multi_threading.h
                codec/encoder/core/inc/stat.h
                codec/encoder/core/inc/svc_base_layer_md.h
                codec/encoder/core/inc/svc_enc_frame.h
                codec/encoder/core/inc/svc_enc_golomb.h
                codec/encoder/core/inc/svc_enc_macroblock.h
                codec/encoder/core/inc/svc_enc_slice_segment.h
                codec/encoder/core/inc/svc_encode_mb.h
                codec/encoder/core/inc/svc_encode_slice.h
                codec/encoder/core/inc/svc_mode_decision.h
                codec/encoder/core/inc/svc_motion_estimate.h
                codec/encoder/core/inc/svc_set_mb_syn.h
                codec/encoder/core/inc/svc_set_mb_syn_cavlc.h
                codec/encoder/core/inc/vlc_encoder.h
                codec/encoder/core/inc/wels_common_basis.h
                codec/encoder/core/inc/wels_const.h
                codec/encoder/core/inc/wels_func_ptr_def.h
                codec/encoder/core/inc/wels_preprocess.h
                codec/encoder/core/inc/wels_task_base.h
                codec/encoder/core/inc/wels_task_encoder.h
                codec/encoder/core/inc/wels_task_management.h
                codec/encoder/core/inc/wels_transpose_matrix.h
                codec/encoder/core/src/au_set.cpp
                codec/encoder/core/src/deblocking.cpp
                codec/encoder/core/src/decode_mb_aux.cpp
                codec/encoder/core/src/encode_mb_aux.cpp
                codec/encoder/core/src/encoder.cpp
                codec/encoder/core/src/encoder_data_tables.cpp
                codec/encoder/core/src/encoder_ext.cpp
                codec/encoder/core/src/get_intra_predictor.cpp
                codec/encoder/core/src/md.cpp
                codec/encoder/core/src/mv_pred.cpp
                codec/encoder/core/src/nal_encap.cpp
                codec/encoder/core/src/paraset_strategy.cpp
                codec/encoder/core/src/picture_handle.cpp
                codec/encoder/core/src/ratectl.cpp
                codec/encoder/core/src/ref_list_mgr_svc.cpp
                codec/encoder/core/src/sample.cpp
                codec/encoder/core/src/set_mb_syn_cabac.cpp
                codec/encoder/core/src/set_mb_syn_cavlc.cpp
                codec/encoder/core/src/slice_multi_threading.cpp
                codec/encoder/core/src/svc_base_layer_md.cpp
                codec/encoder/core/src/svc_enc_slice_segment.cpp
                codec/encoder/core/src/svc_encode_mb.cpp
                codec/encoder/core/src/svc_encode_slice.cpp
                codec/encoder/core/src/svc_mode_decision.cpp
                codec/encoder/core/src/svc_motion_estimate.cpp
                codec/encoder/core/src/svc_set_mb_syn_cabac.cpp
                codec/encoder/core/src/svc_set_mb_syn_cavlc.cpp
                codec/encoder/core/src/wels_preprocess.cpp
                codec/encoder/core/src/wels_task_base.cpp
                codec/encoder/core/src/wels_task_encoder.cpp
                codec/encoder/core/src/wels_task_management.cpp
                codec/encoder/plus/inc/welsEncoderExt.h
                codec/encoder/plus/src/DllEntry.cpp
                codec/encoder/plus/src/welsEncoderExt.cpp
    )
    mcux_add_include(
        INCLUDES codec/encoder/core/inc
                 codec/encoder/plus/inc
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.unused_files)
    mcux_add_source(
        SOURCES LICENSE
                CONTRIBUTORS
                CODING_STYLE
                README.md
                RELEASES
                ChangeLogKSDK.txt
    )
endif()
