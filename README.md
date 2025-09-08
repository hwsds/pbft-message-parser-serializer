# pbft-message-parser-serializer
generic, JSON, Protobuf, BCS, RLP, MessagePack format supported

1. go mod tidy
2. protoc --proto_path=proto --descriptor_set_out=proto/abstraction.protoset --include_imports --include_source_info proto/abstraction.proto (protoset 생성됨)
3. go run ./cmd/testapp (parsing/serializing 테스트용)
