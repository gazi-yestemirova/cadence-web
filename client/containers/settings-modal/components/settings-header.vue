<script>
// Copyright (c) 2017-2023 Uber Technologies Inc.
//
//
// Permission is hereby granted, free of charge, to any person obtaining a copy
// of this software and associated documentation files (the "Software"), to deal
// in the Software without restriction, including without limitation the rights
// to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
// copies of the Software, and to permit persons to whom the Software is
// furnished to do so, subject to the following conditions:
//
// The above copyright notice and this permission notice shall be included in
// all copies or substantial portions of the Software.
//
// THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
// IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
// FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
// AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
// LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
// OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
// THE SOFTWARE.

import { ButtonIcon, FlexGrid, FlexGridItem } from '~components';

export default {
  name: 'settings-header',
  props: {
    title: {
      type: String,
    },
    titleSuffix: {
      type: String,
    },
  },
  computed: {
    displayTitle() {
      const { title, titleSuffix } = this;

      return [title, titleSuffix].join(' ');
    },
  },
  methods: {
    onCloseClick() {
      this.$emit('close');
    },
  },
  components: {
    'button-icon': ButtonIcon,
    'flex-grid': FlexGrid,
    'flex-grid-item': FlexGridItem,
  },
};
</script>

<template>
  <flex-grid align-items="center" class="settings-header">
    <flex-grid-item grow="1">
      <h2>{{ displayTitle }}</h2>
    </flex-grid-item>
    <flex-grid-item width="40px">
      <button-icon icon="icon_delete-thin" size="30px" @click="onCloseClick" />
    </flex-grid-item>
  </flex-grid>
</template>

<style lang="stylus">
.settings-header {
  margin-bottom: 15px;
}
</style>
