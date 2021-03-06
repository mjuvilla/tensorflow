cmake_minimum_required(VERSION 3.1)
project(tensorflow-lite)

set(CMAKE_CXX_STANDARD 11)

# note - this list was obtained by running "make -n" on the Makefile in this directory
set(TENSORFLOW_LITE_SOURCES
    allocation.cc
    arena_planner.cc
    context.c
    downloads/farmhash/src/farmhash.cc
    downloads/fft2d/fftsg.c
    error_reporter.cc
    graph_info.cc
    interpreter.cc
    kernels/activations.cc
    kernels/audio_spectrogram.cc
    kernels/add.cc
    kernels/arg_max.cc
    kernels/basic_rnn.cc
    kernels/batch_to_space_nd.cc
    kernels/bidirectional_sequence_lstm.cc
    kernels/bidirectional_sequence_rnn.cc
    kernels/cast.cc
    kernels/comparisons.cc
    kernels/concatenation.cc
    kernels/conv.cc
    kernels/depthwise_conv.cc
    kernels/detection_postprocess.cc
    kernels/dequantize.cc
    kernels/div.cc
    kernels/eigen_support.cc
    kernels/elementwise.cc
    kernels/embedding_lookup.cc
    kernels/embedding_lookup_sparse.cc
    kernels/expand_dims.cc
    kernels/exp.cc
    kernels/floor.cc
    kernels/fully_connected.cc
    kernels/gather.cc
    kernels/gemm_support.cc
    kernels/hashtable_lookup.cc
    kernels/internal/kernel_utils.cc
    kernels/internal/mfcc.cc
    kernels/internal/mfcc_dct.cc
    kernels/internal/mfcc_mel_filterbank.cc
    kernels/internal/optimized/neon_tensor_utils.cc
    kernels/internal/quantization_util.cc
    kernels/internal/reference/portable_tensor_utils.cc
    kernels/internal/spectrogram.cc
    kernels/internal/tensor_utils.cc
    kernels/kernel_util.cc
    kernels/l2norm.cc
    kernels/local_response_norm.cc
    kernels/lsh_projection.cc
    kernels/lstm.cc
    kernels/maximum_minimum.cc
    kernels/mfcc.cc
    kernels/mul.cc
    kernels/neg.cc
    kernels/pad.cc
    kernels/pooling.cc
    kernels/pow.cc
    kernels/reduce.cc
    kernels/register.cc
    kernels/reshape.cc
    kernels/resize_bilinear.cc
    kernels/shape.cc
    kernels/select.cc
    kernels/slice.cc
    kernels/skip_gram.cc
    kernels/space_to_batch_nd.cc
    kernels/space_to_depth.cc
    kernels/sparse_to_dense.cc
    kernels/split.cc
    kernels/squeeze.cc
    kernels/strided_slice.cc
    kernels/sub.cc
    kernels/svdf.cc
    kernels/tile.cc
    kernels/topk_v2.cc
    kernels/transpose.cc
    kernels/transpose_conv.cc
    kernels/unidirectional_sequence_lstm.cc
    kernels/unidirectional_sequence_rnn.cc
    model.cc
    nnapi_delegate.cc
    optional_debug_tools.cc
    simple_memory_arena.cc
    string_util.cc
    op_resolver.cc
    util.cc
)

add_library(tensorflow-lite STATIC ${TENSORFLOW_LITE_SOURCES})

target_include_directories(tensorflow-lite
    PUBLIC ../../../
    PUBLIC downloads/flatbuffers/include
    PRIVATE downloads
    PRIVATE downloads/eigen
    PRIVATE downloads/fft2d
    PRIVATE downloads/gemmlowp
    PRIVATE downloads/neon_2_sse
    PRIVATE downloads/farmhash/src
    PRIVATE gen/obj
)
