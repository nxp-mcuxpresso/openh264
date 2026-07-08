
if (CONFIG_MCUX_COMPONENT_middleware.openh264.api)
    mcux_component_version(2.6.0)
    mcux_add_source(
        SOURCES codec/api/wels/codec_api.h
                codec/api/wels/codec_app_def.h
                codec/api/wels/codec_def.h
                codec/api/wels/codec_ver.h
    )
    mcux_add_include(
        INCLUDES codec/api/wels
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.common)
    mcux_component_version(2.6.0)
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
                codec/common/inc/loongson_intrinsics.h
                codec/common/inc/ls_defines.h
                codec/common/inc/macros.h
                codec/common/inc/mc.h
                codec/common/inc/measure_time.h
                codec/common/inc/memory_align.h
                codec/common/inc/msa_macros.h
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
        CX "--diag_suppress Pe815,Pe111,Pe186,Pe068,Pe177,Pe550,Pa084"
        CC "--diag_suppress Pe815,Pe111,Pe186,Pe068,Pe177,Pe550,Pa084"
    )

    mcux_add_armgcc_configuration(
        CX "-w\
            -Wno-format\
            -Wno-strict-aliasing\
            -Wno-unused-variable\
            -Wno-unused-but-set-variable\
            -Wno-unused-function\
            -Wno-unused-parameter\
            -Wno-sign-compare\
            -Wno-address\
            -Wno-narrowing\
            -Wno-error\
            -D__INT32_TYPE__=int"

        CC "-w\
            -Wno-address\
            -Wno-unused-variable\
            -Wno-unused-but-set-variable\
            -Wno-error\
            -D__INT32_TYPE__=int"
    )

    mcux_add_mdk_configuration(
        CX "-w\
            -Wno-unused-variable\
            -Wno-unused-function\
            -Wno-unused-parameter"
        CC "-w"
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.procesing)
    mcux_component_version(2.6.0)
    mcux_add_source(
        SOURCES codec/processing/src/adaptivequantization/AdaptiveQuantization.cpp
                codec/processing/src/adaptivequantization/AdaptiveQuantization.h
                codec/processing/src/backgrounddetection/BackgroundDetection.cpp
                codec/processing/src/backgrounddetection/BackgroundDetection.h
                codec/processing/src/common/common.h
                codec/processing/src/common/memory.cpp
                codec/processing/src/common/memory.h
                codec/processing/src/common/resource.h
                codec/processing/src/common/typedef.h
                codec/processing/src/common/util.h
                codec/processing/src/common/WelsFrameWork.cpp
                codec/processing/src/common/WelsFrameWork.h
                codec/processing/src/common/WelsFrameWorkEx.cpp
                codec/processing/src/complexityanalysis/ComplexityAnalysis.cpp
                codec/processing/src/complexityanalysis/ComplexityAnalysis.h
                codec/processing/src/denoise/denoise.cpp
                codec/processing/src/denoise/denoise.h
                codec/processing/src/denoise/denoise_filter.cpp
                codec/processing/src/downsample/downsample.cpp
                codec/processing/src/downsample/downsample.h
                codec/processing/src/downsample/downsamplefuncs.cpp
                codec/processing/src/imagerotate/imagerotate.cpp
                codec/processing/src/imagerotate/imagerotate.h
                codec/processing/src/imagerotate/imagerotatefuncs.cpp
                codec/processing/src/scenechangedetection/SceneChangeDetection.cpp
                codec/processing/src/scenechangedetection/SceneChangeDetection.h
                codec/processing/src/scrolldetection/ScrollDetection.cpp
                codec/processing/src/scrolldetection/ScrollDetection.h
                codec/processing/src/scrolldetection/ScrollDetectionFuncs.cpp
                codec/processing/src/scrolldetection/ScrollDetectionFuncs.h
                codec/processing/src/vaacalc/vaacalcfuncs.cpp
                codec/processing/src/vaacalc/vaacalculation.cpp
                codec/processing/src/vaacalc/vaacalculation.h
                codec/processing/interface/IWelsVP.h
    )

    mcux_add_include(
        INCLUDES codec/processing/interface
                 codec/processing/src/common
                 codec/processing/src/adaptivequantization
                 codec/processing/src/backgrounddetection
                 codec/processing/src/common
                 codec/processing/src/complexityanalysis
                 codec/processing/src/denoise
                 codec/processing/src/downsample
                 codec/processing/src/imagerotate
                 codec/processing/src/scenechangedetection
                 codec/processing/src/scrolldetection
                 codec/processing/src/vaacalc
    )
endif()

if (CONFIG_MCUX_COMPONENT_middleware.openh264.decoder)
    mcux_component_version(2.6.0)
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
    mcux_component_version(2.6.0)
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
    mcux_component_version(2.6.0)
    mcux_add_source(
        SOURCES LICENSE
                CODING_STYLE
                README.md
                RELEASES
                ChangeLogKSDK.txt
    )
endif()
