set(PYTHON_TESTS_DIR ${PADDLE_SOURCE_DIR}/python/paddle/v2/fluid/tests)
cc_test(test_inference_recognize_digits_mlp
    SRCS test_inference_recognize_digits.cc
    DEPS ARCHIVE_START paddle_fluid ARCHIVE_END
    ARGS --dirname=${PYTHON_TESTS_DIR}/book/recognize_digits_mlp.inference.model)
cc_test(test_inference_image_classification_vgg
    SRCS test_inference_image_classification.cc
    DEPS ARCHIVE_START paddle_fluid ARCHIVE_END
    ARGS --dirname=${PYTHON_TESTS_DIR}/book/image_classification_vgg.inference.model)
cc_test(test_inference_image_classification_resnet
    SRCS test_inference_image_classification.cc
    DEPS ARCHIVE_START paddle_fluid ARCHIVE_END
    ARGS --dirname=${PYTHON_TESTS_DIR}/book/image_classification_resnet.inference.model)
cc_test(test_inference_label_semantic_roles
    SRCS test_inference_label_semantic_roles.cc
    DEPS ARCHIVE_START paddle_fluid ARCHIVE_END
    ARGS --dirname=${PYTHON_TESTS_DIR}/book/label_semantic_roles.inference.model)
set_tests_properties(test_inference_recognize_digits_mlp
    PROPERTIES DEPENDS test_recognize_digits)
set_tests_properties(test_inference_image_classification_vgg
    PROPERTIES DEPENDS test_image_classification_train)
set_tests_properties(test_inference_image_classification_resnet
    PROPERTIES DEPENDS test_image_classification_train)
set_tests_properties(test_inference_label_semantic_roles
    PROPERTIES DEPENDS test_label_semantic_roles) 
