# pbft-message-parser-serializer
generic, JSON, Protobuf, BCS, RLP, MessagePack format supported

1. How to setup
  1) install dependencies:
     go mod tidy
  2) generate protobuf descriptor set:
     protoc --proto_path=proto \
     --descriptor_set_out=proto/abstraction.protoset \
     --include_imports --include_source_info proto/abstraction.proto

2. How to run the encoding/decoding testapp
   go run ./cmd/testapp

   * expected output example:
     === Testing format: generic ===
     Serialized 203 bytes
     first 64 bytes (hex): . . .
     Fields match (profiled)
     Mutated: 223 bytes
     mutated first 64 bytes (hex): . . .
     Mutation confirmed: Signature corrupted
     Mutation confirmed: Extras injected (1)
     . . .
     === Synonym mapping tests ===
     Phase synonym: Propose      -> Proposal
     Phase synonym: PrePrepare   -> Proposal
     . . .
     Original JSON: . . .
     Parsed from modified JSON: . . .
